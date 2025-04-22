# LINQ와 비동기 프로그래밍
## LINQ (Language Integrated Query)

LINQ는 C\#에서 데이터 쿼리 기능을 제공하는 기능입니다.

### 쿼리 구문

```csharp
var query = from item in collection
            where item.Property &gt; value
            orderby item.AnotherProperty
            select item;
```


### 메서드 구문

```csharp
var query = collection
    .Where(item => item.Property &gt; value)
    .OrderBy(item => item.AnotherProperty)
    .Select(item => item);
```


## 비동기 프로그래밍

C\#은 async와 await 키워드를 사용하여 비동기 프로그래밍을 지원합니다.

### async/await

```csharp
public async Task<int> DownloadDataAsync()
{
    // 비동기 작업
    var result = await DownloadAsync();
    return result;
}
```


### Task 기반 비동기 패턴

```csharp
public Task<int> GetValueAsync()
{
    return Task.Run(() => {
        // 시간이 오래 걸리는 작업
        return 42;
    });
}
```
