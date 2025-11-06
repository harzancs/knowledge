# Dart / Flutter
Shared Knowledge

```
void main() {
  List<List<String>> listOfItem = [
    ["AA", "BB"],
    ["AA"],
    ["AA"],
  ];

  final mapList = listOfItem.map((e) => e);
  print("Map (${mapList.runtimeType}) : $mapList");
  // ([AA, BB], [AA], [AA])

  // SET
  final setList = listOfItem.toSet();
  print("Set Of List (${setList.runtimeType}) : $setList");
  // {[AA, BB], [AA], [AA]}

  final mapSetList = listOfItem.map((e) => e.toSet()).toList();
  print("List Of Set (${mapSetList.runtimeType}) : $mapSetList");
  // [{AA, BB}, {AA}, {AA}]

  final setListIntersect = mapSetList
      .reduce((a, b) => a.intersection(b))
      .toList();
  print("Set Intersect (${setListIntersect.runtimeType}) : $setListIntersect");
  // [AA]

  final setListUnion = mapSetList.reduce((a, b) => a.union(b)).toList();
  print("Set Union (${setListUnion.runtimeType}) : $setListUnion");
  // [AA, BB]

  final setListDifference = mapSetList
      .reduce((a, b) => a.difference(b))
      .toList();
  print(
    "Set Difference (${setListDifference.runtimeType}) : $setListDifference",
  );
  // [BB]

  // MAP

  final mapListExpend = listOfItem
      .map((e) => e)
      .expand((list) => list)
      .toList();
  print("Map Expend (${mapListExpend.runtimeType}) : $mapListExpend");
  // [AA, BB, AA, AA]

  final listMap = listOfItem.map((e) => {"KEY": e}).toList();
  print("Map List (${listMap.runtimeType}) : $listMap");
  // [{KEY: [AA, BB]}, {KEY: [AA]}, {KEY: [AA]}]

  final listAsMap = listOfItem.asMap();
  print("List As Map (${listAsMap.runtimeType}) : $listAsMap");
  // {0: [AA, BB], 1: [AA], 2: [AA]}

  final listIndexed = listOfItem.indexed.toList();
  print("List Indexed (${listIndexed.runtimeType}) : $listIndexed");
  // [(0, [AA, BB]), (1, [AA]), (2, [AA])]

  final listFollowedBy = listOfItem.followedBy([
    ["CC"],
  ]).toList();
  print("List Followed By (${listFollowedBy.runtimeType}) : $listFollowedBy");
  // [[AA, BB], [AA], [AA], [CC]]

  final listAdd = listOfItem..add(["CC"]);
  print("List Add item (${listAdd.runtimeType}) : $listAdd");
  // [[AA, BB], [AA], [AA], [CC]]

  final listFollowedAsMap = listFollowedBy.toList().asMap();
  print(
    "List Followed By As map (${listFollowedAsMap.runtimeType}) : $listFollowedAsMap",
  ); // {0: [AA, BB], 1: [AA], 2: [AA], 3: [CC]}

  final isListAny = listOfItem.any((e) => e.length == 1);
  print("List is Any (${isListAny.runtimeType}) : $isListAny"); // false

  final isListEvery = listOfItem.every((e) => e.length == 1);
  print("List is Every (${isListEvery.runtimeType}) : $isListEvery"); // false

  final listExpand = listOfItem.expand((list) => list).toList();
  print("List Expand (${listExpand.runtimeType}) : $listExpand");
  // [AA, BB, AA, AA]
}

```
