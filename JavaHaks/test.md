# 컬렉션 프레임워크

## 컬렉션이란?

여러 데이터를 효율적으로 저장, 관리, 처리할 수 있는 자료구조

## 주요 컬렉션 종류

- List: 순서 O, 중복 O (ArrayList, LinkedList 등)
- Set: 순서 X, 중복 X (HashSet, TreeSet 등)
- Map: 키-값 쌍, 키 중복 X (HashMap, TreeMap 등)

## 예시

```

import java.util.*;

List<String> list = new ArrayList<>();
list.add("apple");
list.add("banana");

Set<Integer> set = new HashSet<>();
set.add(1);
set.add(2);

Map<String, Integer> map = new HashMap<>();
map.put("one", 1);
map.put("two", 2);

```
