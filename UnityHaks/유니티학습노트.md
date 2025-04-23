# 유니티로 처음 게임 만들어보기: 탑다운 슈팅 게임 튜토리얼

## 목차

- [개발 환경 설정](#%EA%B0%9C%EB%B0%9C-%ED%99%98%EA%B2%BD-%EC%84%A4%EC%A0%95)
- [프로젝트 생성 및 그래픽 에셋 임포트](#%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EA%B7%B8%EB%9E%98%ED%94%BD-%EC%97%90%EC%85%8B-%EC%9E%84%ED%8F%AC%ED%8A%B8)
- [유니티 인터페이스 설명](#%EC%9C%A0%EB%8B%88%ED%8B%B0-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4-%EC%84%A4%EB%AA%85)
- [타일 맵 만들기](#%ED%83%80%EC%9D%BC-%EB%A7%B5-%EB%A7%8C%EB%93%A4%EA%B8%B0)
- [플레이어 캐릭터 생성](#%ED%94%8C%EB%A0%88%EC%9D%B4%EC%96%B4-%EC%BA%90%EB%A6%AD%ED%84%B0-%EC%83%9D%EC%84%B1)
- [입력과 컨트롤](#%EC%9E%85%EB%A0%A5%EA%B3%BC-%EC%BB%A8%ED%8A%B8%EB%A1%A4)
- [충돌 처리](#%EC%B6%A9%EB%8F%8C-%EC%B2%98%EB%A6%AC)
- [애니메이션](#%EC%95%A0%EB%8B%88%EB%A9%94%EC%9D%B4%EC%85%98)
- [총알 발사](#%EC%B4%9D%EC%95%8C-%EB%B0%9C%EC%82%AC)
- [Prefab](#prefab)
- [오브젝트 풀링](#%EC%98%A4%EB%B8%8C%EC%A0%9D%ED%8A%B8-%ED%92%80%EB%A7%81)
- [적 만들기](#%EC%A0%81-%EB%A7%8C%EB%93%A4%EA%B8%B0)
- [적 스폰하기](#%EC%A0%81-%EC%8A%A4%ED%8F%B0%ED%95%98%EA%B8%B0)
- [게임 UI 표현하기](#%EA%B2%8C%EC%9E%84-ui-%ED%91%9C%ED%98%84%ED%95%98%EA%B8%B0)
- [씬 추가 \& 메뉴 만들기](#%EC%94%AC-%EC%B6%94%EA%B0%80--%EB%A9%94%EB%89%B4-%EB%A7%8C%EB%93%A4%EA%B8%B0)
- [사운드 제작 및 플레이](#%EC%82%AC%EC%9A%B4%EB%93%9C-%EC%A0%9C%EC%9E%91-%EB%B0%8F-%ED%94%8C%EB%A0%88%EC%9D%B4)
- [마무리](#%EB%A7%88%EB%AC%B4%EB%A6%AC)


## 개발 환경 설정

이 튜토리얼을 따라하기 위해 필요한 소프트웨어와 자료:

- Unity Hub 및 Unity 2022 버전 설치
- 기본적인 C\# 프로그래밍 지식
- [Tech Dungeon: Roguelite](https://trevor-pupkin.itch.io/tech-dungeon-roguelite) 무료 에셋

개발 환경 설정에 대한 자세한 내용은 [이 영상](https://www.youtube.com/watch?v=GA9PoVl9w4A)을 참고하세요.
C\# 기초 강좌는 [이 재생목록](https://www.youtube.com/playlist?list=PLNKlzpnLyknqNmHnzZIJYyD08SUT_ErjZ)을 참고하세요.

> **이미지 추가**: 여기에 Unity Hub 설치 화면과 Unity 에디터 시작 화면 스크린샷을 추가하세요 (01_unity_installation.png)

## 프로젝트 생성 및 그래픽 에셋 임포트

### 프로젝트 생성

1. Unity Hub를 실행하고 "새 프로젝트"를 클릭합니다.
2. 템플릿에서 "2D"를 선택합니다.
3. 프로젝트 이름을 "미니건전"으로 지정하고 생성합니다.

> **이미지 추가**: 유니티 프로젝트 생성 화면 스크린샷 (02_project_creation.png)

### 그래픽 에셋 다운로드

1. itch.io에서 [Tech Dungeon: Roguelite](https://trevor-pupkin.itch.io/tech-dungeon-roguelite) 에셋을 다운로드합니다.
2. 다운로드한 파일을 압축 해제합니다.

> **이미지 추가**: Tech Dungeon Roguelite 에셋 다운로드 페이지 스크린샷 (03_asset_download.png)

### 에셋 임포트

1. 유니티 프로젝트에서 Assets 폴더 아래 "Sprites" 폴더를 생성합니다.
2. 다운로드한 그래픽 파일을 Sprites 폴더로 드래그합니다.
3. tileset 스프라이트를 선택하고 Inspector에서 다음 설정을 변경합니다:
    - Sprite Mode: Single → Multiple
    - Pixels Per Unit: 32
    - Filter Mode: Bilinear → Point
4. Apply 버튼을 클릭합니다.
5. Sprite Editor를 열고 Slice 버튼을 클릭합니다.
6. Type: Grid by Cell Size, X: 32, Y: 32로 설정하고 Slice를 클릭합니다.
7. Apply를 클릭하여 설정을 저장합니다.

> **이미지 추가**:
> - 스프라이트 설정 변경 화면 (04_sprite_settings.png)
> - 스프라이트 에디터 슬라이싱 화면 (05_sprite_slicing.png)

## 유니티 인터페이스 설명

유니티 에디터의 주요 창:

- **Hierarchy 창**: 현재 씬에 있는 모든 게임 오브젝트를 보여줍니다.
- **Inspector 창**: 선택한 게임 오브젝트의 속성과 컴포넌트를 보여줍니다.
- **Project 창**: 프로젝트의 모든 에셋과 폴더를 보여줍니다.
- **Scene 창**: 게임 월드를 편집할 수 있는 공간입니다.
- **Game 창**: 게임이 실행될 때 플레이어가 보게 될 화면입니다.

> **이미지 추가**: 유니티 에디터의 전체 인터페이스 화면 스크린샷, 각 주요 창에 라벨을 표시 (06_unity_interface.png)

## 타일 맵 만들기

### 타일 팔레트 설정

1. Window > 2D > Tile Palette 메뉴를 선택합니다.
2. Create New Palette를 클릭하고 이름을 "Floor"로 지정합니다.
3. 저장 위치로 Assets 아래 새 "Tiles" 폴더를 생성하고 선택합니다.
4. 자른 tileset 스프라이트를 타일 팔레트에 드래그합니다.

> **이미지 추가**: 타일 팔레트 생성 및 설정 화면 (07_tile_palette.png)

### 바닥 타일맵 생성

1. Hierarchy 창에서 우클릭 > 2D Object > Tilemap > Rectangular를 선택합니다.
2. 생성된 타일맵의 이름을 "Floor"로 변경합니다.
3. 타일 팔레트에서 바닥 타일을 선택하고 Scene 창에 그립니다.

### 벽 타일맵 생성

1. Grid 오브젝트에서 우클릭 > 2D Object > Tilemap > Rectangular를 선택합니다.
2. 생성된 타일맵의 이름을 "Wall"로 변경합니다.
3. 타일 팔레트에서 벽 타일을 선택하고 Scene 창에 그립니다.

> **이미지 추가**:
> - 타일맵 생성 과정 스크린샷 (08_tilemap_creation.png)
> - 바닥과 벽 타일을 배치한 최종 결과물 (09_tilemap_result.png)

### Sorting Layer 설정

1. 두 타일맵을 선택하고 Inspector에서 Additional Settings를 확장합니다.
2. Add Sorting Layer를 클릭하고 "Background"라는 새 레이어를 추가합니다.
3. Floor와 Wall 타일맵의 Sorting Layer를 "Background"로 설정합니다.
4. Floor의 Order in Layer를 0, Wall의 Order in Layer를 1로 설정합니다.

> **이미지 추가**: Sorting Layer 설정 화면 (10_sorting_layers.png)

## 플레이어 캐릭터 생성

1. Hierarchy 창에서 우클릭 > 2D Object > Sprite > Circle을 선택합니다.
2. 생성된 오브젝트의 이름을 "Player"로 변경합니다.
3. Add Sorting Layer를 클릭하고 "Character"라는 새 레이어를 추가합니다.
4. Player의 Sorting Layer를 "Character"로 설정합니다.
5. 플레이어 스프라이트를 임포트합니다:
    - players_blue_x1 스프라이트를 선택합니다
    - Sprite Mode: Single → Multiple
    - Pixels Per Unit: 16 (캐릭터 크기를 조정하기 위해)
    - Filter Mode: Point
    - Sprite Editor를 열고 슬라이스 설정 (Grid by Cell Size, X: 32, Y: 32)
6. 슬라이스된 플레이어 스프라이트 중 하나를 Player 오브젝트에 드래그합니다.

> **이미지 추가**:
> - 플레이어 오브젝트 생성 화면 (11_player_creation.png)
> - 플레이어 스프라이트 설정 화면 (12_player_sprite_settings.png)
> - 최종 플레이어 캐릭터 모습 (13_player_character.png)

## 입력과 컨트롤

### PlayerController 스크립트 생성

1. Assets 폴더에 "Scripts" 폴더를 생성합니다.
2. Scripts 폴더에서 우클릭 > Create > C\# Script를 선택하고 "PlayerController"라고 이름을 지정합니다.
3. 스크립트를 Player 오브젝트에 드래그합니다.
4. 스크립트를 더블 클릭하여 편집기에서 엽니다.

> **이미지 추가**: 스크립트 폴더 생성 및 PlayerController 스크립트 생성 화면 (14_script_creation.png)

### 플레이어 이동 구현

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 8f;
    private Vector2 move;

    void Update()
    {
        // 입력 감지
        move = Vector2.zero;
        
        if (Input.GetKey(KeyCode.LeftArrow) || Input.GetKey(KeyCode.A))
        {
            move += Vector2.left;
        }
        
        if (Input.GetKey(KeyCode.RightArrow) || Input.GetKey(KeyCode.D))
        {
            move += Vector2.right;
        }
        
        if (Input.GetKey(KeyCode.UpArrow) || Input.GetKey(KeyCode.W))
        {
            move += Vector2.up;
        }
        
        if (Input.GetKey(KeyCode.DownArrow) || Input.GetKey(KeyCode.S))
        {
            move += Vector2.down;
        }

        // 스프라이트 방향 설정
        if (move.x &lt; 0)
        {
            GetComponent&lt;SpriteRenderer&gt;().flipX = true;
        }
        else if (move.x &gt; 0)
        {
            GetComponent&lt;SpriteRenderer&gt;().flipX = false;
        }
    }

    void FixedUpdate()
    {
        // 정규화해서 대각선 이동 속도 조정
        if (move.magnitude &gt; 0)
        {
            move.Normalize();
            transform.Translate(move * speed * Time.fixedDeltaTime);
        }
    }
}
```

> **이미지 추가**:
> - PlayerController 스크립트 편집 화면 (15_player_controller_script.png)
> - 캐릭터가 움직이는 모습을 보여주는 연속 스크린샷 또는 GIF (16_player_movement.gif)

### 카메라 설정

1. Main Camera를 선택하고 Player 오브젝트에 드래그해 자식으로 만듭니다.
2. Main Camera의 Position을 (0, 0, -10)으로 설정합니다.
3. Player의 Position을 (0, 0, 0)으로 설정합니다.

> **이미지 추가**: 카메라 설정 화면 (17_camera_setup.png)

## 충돌 처리

### 플레이어 콜라이더 설정

1. Player 오브젝트를 선택하고 Add Component > Physics 2D > Circle Collider 2D를 추가합니다.
2. Circle Collider 2D의 크기를 플레이어 스프라이트에 맞게 조정합니다.
3. Add Component > Physics 2D > Rigidbody 2D를 추가합니다.
4. Rigidbody 2D의 Gravity Scale을 0으로 설정합니다.

> **이미지 추가**: 플레이어 콜라이더 및 Rigidbody 설정 화면 (18_player_collider.png)

### 벽 콜라이더 설정

1. Wall 타일맵을 선택하고 Add Component > Tilemap > Tilemap Collider 2D를 추가합니다.
2. Add Component > Physics 2D > Rigidbody 2D를 추가합니다.
3. Rigidbody 2D의 Body Type을 Static으로 설정합니다.
4. Gravity Scale을 0으로 설정합니다.

> **이미지 추가**:
> - 벽 타일맵 콜라이더 설정 화면 (19_wall_collider.png)
> - 플레이어가 벽과 충돌하는 모습 (20_collision_test.gif)

## 애니메이션

### 애니메이터 컴포넌트 추가

1. Player 오브젝트를 선택하고 Add Component > Animator를 추가합니다.
2. Assets 폴더에 "Animation" 폴더를 생성합니다.
3. Animation 폴더에서 우클릭 > Create > Animator Controller를 선택하고 "PlayerAnimator"라고 이름을 지정합니다.
4. PlayerAnimator를 Player 오브젝트의 Animator 컴포넌트에 드래그합니다.

> **이미지 추가**: 애니메이터 컴포넌트 설정 화면 (21_animator_component.png)

### 애니메이션 클립 생성

1. Window > Animation > Animation을 선택합니다.
2. Player 오브젝트를 선택하고 Create를 클릭합니다.
3. "PlayerIdle"이라는 애니메이션 클립을 생성하고 Animation 폴더에 저장합니다.
4. 플레이어의 대기 스프라이트를 타임라인에 추가합니다.
5. Create New Clip을 클릭하고 "PlayerRun"이라는 새 애니메이션을 생성합니다.
6. Samples를 8로 설정합니다.
7. 플레이어의 달리기 스프라이트 4장을 타임라인에 추가합니다.

> **이미지 추가**:
> - 애니메이션 창과 타임라인 설정 화면 (22_animation_timeline.png)
> - PlayerIdle 및 PlayerRun 애니메이션 프레임 (23_animation_frames.png)

### 애니메이션 전환 설정

1. Animator 창을 열고 Parameters 탭에서 Trigger 타입의 "Move"와 "Stop" 파라미터를 추가합니다.
2. PlayerIdle 상태에서 우클릭 > Make Transition을 선택하고 PlayerRun 상태로 연결합니다.
    - Has Exit Time 체크 해제
    - Duration을 0으로 설정
    - Condition으로 Move 트리거 추가
3. PlayerRun 상태에서 PlayerIdle 상태로 전환을 만듭니다.
    - Has Exit Time 체크 해제
    - Duration을 0으로 설정
    - Condition으로 Stop 트리거 추가

> **이미지 추가**: 애니메이터 컨트롤러 그래프 설정 화면 (24_animator_controller.png)

### 애니메이션 트리거 설정

PlayerController 스크립트를 수정합니다:

```csharp
// Update 함수 내에 다음 코드 추가
if (move.magnitude &gt; 0)
{
    GetComponent&lt;Animator&gt;().SetTrigger("Move");
}
else
{
    GetComponent&lt;Animator&gt;().SetTrigger("Stop");
}
```

> **이미지 추가**: 애니메이션이 적용된 캐릭터 움직임 GIF (25_player_animation.gif)

## 총알 발사

### 총알 오브젝트 생성

1. Hierarchy 창에서 우클릭 > 2D Object > Sprite > Circle을 선택합니다.
2. 생성된 오브젝트의 이름을 "Bullet"으로 변경합니다.
3. Add Sorting Layer에서 "Effect" 레이어를 생성하고 Bullet의 Sorting Layer로 설정합니다.
4. Bullet의 색상을 파란색으로 변경하고 Scale을 (0.5, 0.5, 1)로 설정합니다.
5. Add Component > Physics 2D > Circle Collider 2D를 추가합니다.
6. Circle Collider 2D의 Is Trigger를 체크합니다.
7. Add Component > Physics 2D > Rigidbody 2D를 추가하고 Gravity Scale을 0으로 설정합니다.

> **이미지 추가**: 총알 오브젝트 설정 화면 (26_bullet_setup.png)

### 총알 스크립트 생성

1. Scripts 폴더에서 우클릭 > Create > C\# Script를 선택하고 "Bullet"이라고 이름을 지정합니다.
2. 스크립트를 Bullet 오브젝트에 드래그합니다.
3. 스크립트를 다음과 같이 작성합니다:
```csharp
using UnityEngine;

public class Bullet : MonoBehaviour
{
    public float speed = 15f;
    public int damage = 1;
    private Vector2 direction;

    public Vector2 Direction
    {
        set { direction = value.normalized; }
    }

    void Update()
    {
        transform.Translate(direction * speed * Time.deltaTime);
    }

    void OnTriggerEnter2D(Collider2D collision)
    {
        if (collision.CompareTag("Wall"))
        {
            Destroy(gameObject);
        }
    }
}
```

> **이미지 추가**: Bullet 스크립트 편집 화면 (27_bullet_script.png)

### 태그 설정

1. Bullet 오브젝트를 선택하고 Tag 드롭다운에서 Add Tag를 클릭합니다.
2. "Wall", "Bullet", "Enemy" 태그를 추가합니다.
3. Wall 타일맵에 "Wall" 태그를 설정합니다.
4. Bullet 오브젝트에 "Bullet" 태그를 설정합니다.

> **이미지 추가**: 태그 설정 화면 (28_tag_setup.png)

## Prefab

### 총알 프리팹 생성

1. Assets 폴더에 "Prefabs" 폴더를 생성합니다.
2. Bullet 오브젝트를 Hierarchy에서 Prefabs 폴더로 드래그합니다.
3. Hierarchy에서 Bullet 오브젝트를 삭제합니다.

> **이미지 추가**:
> - Prefabs 폴더 생성 및 총알 프리팹 생성 화면 (29_prefab_creation.png)
> - 프리팹과 인스턴스의 차이점을 보여주는 비교 이미지 (30_prefab_vs_instance.png)

### PlayerController에 총알 발사 기능 추가

PlayerController 스크립트를 다음과 같이 수정합니다:

```csharp
// 클래스 상단에 추가
public GameObject bulletPrefab;

// Update 함수 내에 추가
if (Input.GetMouseButtonDown(0))
{
    Shoot();
}

// 새 함수 추가
void Shoot()
{
    GameObject newBullet = Instantiate(bulletPrefab);
    newBullet.transform.position = transform.position + new Vector3(0, -0.5f, 0);
    
    Vector3 worldPosition = Camera.main.ScreenToWorldPoint(Input.mousePosition);
    worldPosition.z = 0;
    
    Vector2 direction = worldPosition - transform.position;
    newBullet.GetComponent&lt;Bullet&gt;().Direction = direction;
}
```

4. Player 오브젝트를 선택하고 Inspector에서 Bullet Prefab 필드에 총알 프리팹을 드래그합니다.

> **이미지 추가**:
> - PlayerController에 총알 발사 기능 추가 코드 화면 (31_shoot_function.png)
> - Player 인스펙터에서 Bullet Prefab 할당 화면 (32_bullet_prefab_assignment.png)
> - 플레이어가 총알을 발사하는 모습 GIF (33_bullet_shooting.gif)

## 오브젝트 풀링

게임 성능을 향상시키기 위해 오브젝트 풀링을 구현합니다. 오브젝트 풀링은 게임 오브젝트를 계속 생성하고 파괴하는 대신, 미리 만들어둔 오브젝트를 재사용하는 기법입니다.

### ObjectPool 스크립트 생성

1. Scripts 폴더에서 우클릭 > Create > C\# Script를 선택하고 "ObjectPool"이라고 이름을 지정합니다.
2. 스크립트를 다음과 같이 작성합니다:
```csharp
using System.Collections.Generic;
using UnityEngine;

public class ObjectPool : MonoBehaviour
{
    public static ObjectPool Instance;

    [System.Serializable]
    public class Pool
    {
        public string tag;
        public GameObject prefab;
        public int size;
    }

    public List&lt;Pool&gt; pools;
    private Dictionary&lt;string, Queue&lt;GameObject&gt;&gt; poolDictionary;

    void Awake()
    {
        Instance = this;
    }

    void Start()
    {
        poolDictionary = new Dictionary&lt;string, Queue&lt;GameObject&gt;&gt;();

        foreach (Pool pool in pools)
        {
            Queue&lt;GameObject&gt; objectPool = new Queue&lt;GameObject&gt;();

            for (int i = 0; i &lt; pool.size; i++)
            {
                GameObject obj = Instantiate(pool.prefab);
                obj.SetActive(false);
                objectPool.Enqueue(obj);
            }

            poolDictionary.Add(pool.tag, objectPool);
        }
    }

    public GameObject SpawnFromPool(string tag, Vector3 position, Quaternion rotation)
    {
        if (!poolDictionary.ContainsKey(tag))
        {
            Debug.LogWarning("Pool with tag " + tag + " doesn't exist.");
            return null;
        }

        GameObject objectToSpawn = poolDictionary[tag].Dequeue();

        objectToSpawn.SetActive(true);
        objectToSpawn.transform.position = position;
        objectToSpawn.transform.rotation = rotation;

        poolDictionary[tag].Enqueue(objectToSpawn);

        return objectToSpawn;
    }
}
```

> **이미지 추가**: ObjectPool 스크립트 편집 화면 (34_object_pool_script.png)

### 오브젝트 풀 설정

1. Hierarchy 창에서 우클릭 > Create Empty를 선택하고 이름을 "ObjectPool"로 지정합니다.
2. ObjectPool 스크립트를 ObjectPool 오브젝트에 드래그합니다.
3. Inspector에서 Pools 필드의 Size를 1로 설정합니다.
4. Element 0의 Tag를 "Bullet", Prefab에 총알 프리팹을 드래그하고, Size를 20으로 설정합니다.

> **이미지 추가**: 오브젝트 풀 인스펙터 설정 화면 (35_object_pool_setup.png)

### Bullet 스크립트 수정

Bullet 스크립트를 수정하여 Destroy 대신 비활성화하도록 합니다:

```csharp
void OnTriggerEnter2D(Collider2D collision)
{
    if (collision.CompareTag("Wall"))
    {
        gameObject.SetActive(false);
    }
}
```


### PlayerController 수정

PlayerController의 Shoot 함수를 수정합니다:

```csharp
void Shoot()
{
    GameObject newBullet = ObjectPool.Instance.SpawnFromPool("Bullet", transform.position + new Vector3(0, -0.5f, 0), Quaternion.identity);
    
    if (newBullet != null)
    {
        Vector3 worldPosition = Camera.main.ScreenToWorldPoint(Input.mousePosition);
        worldPosition.z = 0;
        
        Vector2 direction = worldPosition - transform.position;
        newBullet.GetComponent&lt;Bullet&gt;().Direction = direction;
    }
}
```

> **이미지 추가**:
> - 오브젝트 풀링 개념 설명 다이어그램 (36_object_pooling_concept.png)
> - 오브젝트 풀링이 적용된 총알 발사 모습 GIF (37_object_pooling_bullets.gif)

## 적 만들기

### 적 오브젝트 생성

1. Hierarchy 창에서 우클릭 > 2D Object > Sprite > Square를 선택합니다.
2. 생성된 오브젝트의 이름을 "Enemy"로 변경합니다.
3. Enemy의 Sorting Layer를 "Character"로 설정하고 Order in Layer를 0으로 설정합니다.
4. 적 스프라이트를 임포트하고 Enemy 오브젝트에 적용합니다.
5. Add Component > Physics 2D > Box Collider 2D를 추가합니다.
6. Add Component > Physics 2D > Rigidbody 2D를 추가하고 Gravity Scale을 0으로 설정합니다.
7. Tag를 "Enemy"로 설정합니다.

> **이미지 추가**: 적 캐릭터 설정 화면 (38_enemy_setup.png)

### Enemy 스크립트 생성

1. Scripts 폴더에서 우클릭 > Create > C\# Script를 선택하고 "Enemy"라고 이름을 지정합니다.
2. 스크립트를 Enemy 오브젝트에 드래그합니다.
3. 스크립트를 다음과 같이 작성합니다:
```csharp
using UnityEngine;

public class Enemy : MonoBehaviour
{
    public float speed = 3f;
    public int health = 3;
    public int damage = 1;
    
    private Transform player;
    
    void Start()
    {
        player = GameObject.FindGameObjectWithTag("Player").transform;
    }
    
    void Update()
    {
        if (player != null)
        {
            // 플레이어 방향으로 이동
            Vector2 direction = player.position - transform.position;
            direction.Normalize();
            
            transform.Translate(direction * speed * Time.deltaTime);
            
            // 스프라이트 방향 설정
            if (direction.x &lt; 0)
            {
                GetComponent&lt;SpriteRenderer&gt;().flipX = true;
            }
            else if (direction.x &gt; 0)
            {
                GetComponent&lt;SpriteRenderer&gt;().flipX = false;
            }
        }
    }
    
    void OnTriggerEnter2D(Collider2D collision)
    {
        if (collision.CompareTag("Bullet"))
        {
            TakeDamage(collision.gameObject.GetComponent&lt;Bullet&gt;().damage);
            collision.gameObject.SetActive(false);
        }
    }
    
    void TakeDamage(int damage)
    {
        health -= damage;
        
        if (health &lt;= 0)
        {
            gameObject.SetActive(false);
        }
    }
}
```

> **이미지 추가**: Enemy 스크립트 편집 화면 (39_enemy_script.png)

### 적 프리팹 만들기

1. Enemy 오브젝트를 Prefabs 폴더로 드래그합니다.
2. Hierarchy에서 Enemy 오브젝트를 삭제합니다.
3. 오브젝트 풀에 Enemy 풀을 추가합니다.

> **이미지 추가**: 적 프리팹 생성 화면 (40_enemy_prefab.png)

## 적 스폰하기

### EnemySpawner 스크립트 생성

1. Hierarchy 창에서 우클릭 > Create Empty를 선택하고 이름을 "EnemySpawner"로 지정합니다.
2. Scripts 폴더에서 우클릭 > Create > C\# Script를 선택하고 "EnemySpawner"라고 이름을 지정합니다.
3. 스크립트를 EnemySpawner 오브젝트에 드래그합니다.
4. 스크립트를 다음과 같이 작성합니다:
```csharp
using System.Collections;
using UnityEngine;

public class EnemySpawner : MonoBehaviour
{
    public float spawnRate = 1f;
    public float spawnDistance = 10f;
    public GameObject enemyPrefab;
    
    private Transform player;
    
    void Start()
    {
        player = GameObject.FindGameObjectWithTag("Player").transform;
        StartCoroutine(SpawnEnemies());
    }
    
    IEnumerator SpawnEnemies()
    {
        while (true)
        {
            yield return new WaitForSeconds(1f / spawnRate);
            
            if (player != null)
            {
                Vector2 spawnDirection = Random.insideUnitCircle.normalized;
                Vector3 spawnPosition = player.position + new Vector3(spawnDirection.x, spawnDirection.y, 0) * spawnDistance;
                
                GameObject enemy = ObjectPool.Instance.SpawnFromPool("Enemy", spawnPosition, Quaternion.identity);
                
                if (enemy == null)
                {
                    enemy = Instantiate(enemyPrefab, spawnPosition, Quaternion.identity);
                    enemy.SetActive(true);
                }
            }
        }
    }
}
```

5. EnemySpawner 오브젝트의 Inspector에서 Enemy Prefab 필드에 적 프리팹을 드래그합니다.

> **이미지 추가**:
> - EnemySpawner 스크립트 편집 화면 (41_enemy_spawner_script.png)
> - 적 스포너 설정 화면 (42_enemy_spawner_setup.png)
> - 적이 스폰되는 과정을 보여주는 GIF (43_enemy_spawning.gif)

## 게임 UI 표현하기

### 체력 표시 UI 만들기

1. Hierarchy 창에서 우클릭 > UI > Canvas를 선택합니다.
2. Canvas 내에 우클릭 > UI > Slider를 선택합니다.
3. Slider의 이름을 "HealthBar"로 변경합니다.
4. RectTransform을 수정하여 화면 상단에 위치시킵니다.
5. Fill 이미지의 색상을 빨간색으로 변경합니다.

> **이미지 추가**: 체력 바 UI 설정 화면 (44_health_bar_setup.png)

### 점수 표시 UI 만들기

1. Canvas 내에 우클릭 > UI > Text를 선택합니다.
2. Text의 이름을 "ScoreText"로 변경합니다.
3. 텍스트를 "Score: 0"으로, 폰트 크기를 적절하게 설정합니다.
4. RectTransform을 수정하여 화면 우측 상단에 위치시킵니다.

> **이미지 추가**: 점수 텍스트 UI 설정 화면 (45_score_text_setup.png)

### GameManager 스크립트 생성

1. Hierarchy 창에서 우클릭 > Create Empty를 선택하고 이름을 "GameManager"로 지정합니다.
2. Scripts 폴더에서 우클릭 > Create > C\# Script를 선택하고 "GameManager"라고 이름을 지정합니다.
3. 스크립트를 GameManager 오브젝트에 드래그합니다.
4. 스크립트를 다음과 같이 작성합니다:
```csharp
using UnityEngine;
using UnityEngine.UI;

public class GameManager : MonoBehaviour
{
    public static GameManager Instance;
    
    public int maxHealth = 100;
    public int currentHealth;
    public int score = 0;
    
    public Slider healthBar;
    public Text scoreText;
    
    void Awake()
    {
        Instance = this;
        currentHealth = maxHealth;
    }
    
    void Start()
    {
        UpdateHealthBar();
        UpdateScoreText();
    }
    
    public void TakeDamage(int damage)
    {
        currentHealth -= damage;
        
        if (currentHealth &lt;= 0)
        {
            GameOver();
        }
        
        UpdateHealthBar();
    }
    
    public void AddScore(int points)
    {
        score += points;
        UpdateScoreText();
    }
    
    void UpdateHealthBar()
    {
        if (healthBar != null)
        {
            healthBar.value = (float)currentHealth / maxHealth;
        }
    }
    
    void UpdateScoreText()
    {
        if (scoreText != null)
        {
            scoreText.text = "Score: " + score;
        }
    }
    
    void GameOver()
    {
        Debug.Log("Game Over");
        // 게임 오버 처리
    }
}
```

5. GameManager 오브젝트의 Inspector에서 Health Bar 필드에 HealthBar 슬라이더를, Score Text 필드에 ScoreText를 드래그합니다.

> **이미지 추가**:
> - GameManager 스크립트 편집 화면 (46_game_manager_script.png)
> - GameManager 인스펙터 설정 화면 (47_game_manager_setup.png)

### Player 스크립트에 데미지 로직 추가

PlayerController 스크립트에 다음 함수를 추가합니다:

```csharp
void OnTriggerEnter2D(Collider2D collision)
{
    if (collision.CompareTag("Enemy"))
    {
        GameManager.Instance.TakeDamage(collision.gameObject.GetComponent&lt;Enemy&gt;().damage);
    }
}
```


### Enemy 스크립트에 점수 추가 로직 추가

Enemy 스크립트의 TakeDamage 함수를 수정합니다:

```csharp
void TakeDamage(int damage)
{
    health -= damage;
    
    if (health &lt;= 0)
    {
        GameManager.Instance.AddScore(10);
        gameObject.SetActive(false);
    }
}
```

> **이미지 추가**: 최종 게임 UI가 표시된 게임 화면 (48_game_ui_in_action.png)

## 씬 추가 \& 메뉴 만들기

### 메인 메뉴 씬 생성

1. File > New Scene을 선택합니다.
2. 씬을 "MainMenu"로 저장합니다.
3. Hierarchy 창에서 우클릭 > UI > Canvas를 선택합니다.
4. Canvas 내에 우클릭 > UI > Button을 선택하고 이름을 "StartButton"으로 변경합니다.
5. Button 텍스트를 "Start Game"으로 변경합니다.
6. Canvas 내에 또 다른 Button을 추가하고 이름을 "QuitButton"으로 변경합니다.
7. Button 텍스트를 "Quit"으로 변경합니다.

> **이미지 추가**: 메인 메뉴 씬 디자인 화면 (49_main_menu_design.png)

### MenuManager 스크립트 생성

1. Scripts 폴더에서 우클릭 > Create > C\# Script를 선택하고 "MenuManager"라고 이름을 지정합니다.
2. 스크립트를 다음과 같이 작성합니다:
```csharp
using UnityEngine;
using UnityEngine.SceneManagement;

public class MenuManager : MonoBehaviour
{
    public void StartGame()
    {
        SceneManager.LoadScene("GameScene");
    }
    
    public void QuitGame()
    {
        #if UNITY_EDITOR
            UnityEditor.EditorApplication.isPlaying = false;
        #else
            Application.Quit();
        #endif
    }
}
```

3. MainMenu 씬의 Canvas에 빈 게임 오브젝트를 생성하고 이름을 "MenuManager"로 지정합니다.
4. MenuManager 스크립트를 MenuManager 오브젝트에 드래그합니다.
5. StartButton의 OnClick() 이벤트에 MenuManager 오브젝트를 추가하고 MenuManager.StartGame 함수를 선택합니다.
6. QuitButton의 OnClick() 이벤트에 MenuManager 오브젝트를 추가하고 MenuManager.QuitGame 함수를 선택합니다.

> **이미지 추가**:
> - MenuManager 스크립트 편집 화면 (50_menu_manager_script.png)
> - 버튼 OnClick 이벤트 설정 화면 (51_button_events.png)

### 게임 씬 저장 및 씬 관리

1. 현재 작업 중인 게임 씬을 "GameScene"으로 저장합니다.
2. File > Build Settings를 열고 "Add Open Scenes"를 클릭하여 두 씬을 빌드 설정에 추가합니다.
3. MainMenu 씬을 첫 번째 씬으로 설정합니다.

> **이미지 추가**: 빌드 설정 창 스크린샷 (52_build_settings.png)

## 사운드 제작 및 플레이

### 사운드 에셋 임포트

1. Assets 폴더에 "Sounds" 폴더를 생성합니다.
2. 필요한 사운드 파일을 Sounds 폴더로 임포트합니다:
    - 배경 음악
    - 총알 발사 효과음
    - 적 피격 효과음
    - 플레이어 피격 효과음

> **이미지 추가**: 사운드 폴더와 임포트된 사운드 파일 (53_sound_assets.png)

### AudioManager 스크립트 생성

1. Hierarchy 창에서 우클릭 > Create Empty를 선택하고 이름을 "AudioManager"로 지정합니다.
2. Scripts 폴더에서 우클릭 > Create > C\# Script를 선택하고 "AudioManager"라고 이름을 지정합니다.
3. 스크립트를 AudioManager 오브젝트에 드래그합니다.
4. 스크립트를 다음과 같이 작성합니다:
```csharp
using UnityEngine;

public class AudioManager : MonoBehaviour
{
    public static AudioManager Instance;
    
    public AudioSource musicSource;
    public AudioSource effectsSource;
    
    public AudioClip shootSound;
    public AudioClip enemyHitSound;
    public AudioClip playerHitSound;
    
    void Awake()
    {
        if (Instance == null)
        {
            Instance = this;
            DontDestroyOnLoad(gameObject);
        }
        else
        {
            Destroy(gameObject);
        }
    }
    
    public void PlayShootSound()
    {
        effectsSource.PlayOneShot(shootSound);
    }
    
    public void PlayEnemyHitSound()
    {
        effectsSource.PlayOneShot(enemyHitSound);
    }
    
    public void PlayPlayerHitSound()
    {
        effectsSource.PlayOneShot(playerHitSound);
    }
}
```

5. AudioManager 오브젝트에 Audio Source 컴포넌트를 두 개 추가합니다.
6. 첫 번째 Audio Source를 musicSource로, 두 번째를 effectsSource로 설정합니다.
7. Inspector에서 음향 클립을 해당 필드에 드래그합니다.

> **이미지 추가**:
> - AudioManager 스크립트 편집 화면 (54_audio_manager_script.png)
> - 오디오 매니저 인스펙터 설정 화면 (55_audio_manager_setup.png)

### 사운드 트리거 추가

1. PlayerController의 Shoot 함수에 사운드 재생을 추가합니다:
```csharp
void Shoot()
{
    // 기존 코드
    
    AudioManager.Instance.PlayShootSound();
}
```

2. Enemy의 TakeDamage 함수에 사운드 재생을 추가합니다:
```csharp
void TakeDamage(int damage)
{
    // 기존 코드
    
    AudioManager.Instance.PlayEnemyHitSound();
    
    // 기존 코드
}
```

3. PlayerController의 OnTriggerEnter2D 함수에 사운드 재생을 추가합니다:
```csharp
void OnTriggerEnter2D(Collider2D collision)
{
    if (collision.CompareTag("Enemy"))
    {
        GameManager.Instance.TakeDamage(collision.gameObject.GetComponent&lt;Enemy&gt;().damage);
        AudioManager.Instance.PlayPlayerHitSound();
    }
}
```

> **이미지 추가**: 사운드 트리거가 적용된 게임 플레이 화면 (56_sound_in_action.gif)


