# Check Array Formation Through Concatenation

~~~java
class Solution {
    public boolean canFormArray(int[] arr, int[][] pieces) {
        List<Integer> list = Arrays.stream(arr).boxed().collect(Collectors.toList());
        for (int[] pieceElement : pieces) {
          int index = list.indexOf(pieceElement[0]);
          for (int e : pieceElement) {
            if (index == -1 || index >= list.size() || list.get(index) != e) {
              return false;
            }
            index++;
          }
        }
        return true;
    }
}
~~~

