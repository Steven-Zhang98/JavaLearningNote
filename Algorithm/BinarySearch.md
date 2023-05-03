``` java
public static int binarySearch(int[] a, int target) {
        int i = 0, j = a.length;
        while (i < j) {
            int m = i + j >>> 1;
            if (target < a[m]) {
                j = m;
            } else if (a[m] < target) {
                i = m + 1;
            } else {
                return m;
            }
        }
        return -1;
    }
```
