



```java
// you can also use imports, for example:
import java.util.*;

// you can write to stdout for debugging purposes, e.g.
// System.out.println("this is a debug message");

class Solution {
    public int[] solution(int N, int[] A) {
        // write your code in Java SE 8
        
        int[] result = new int[N];
        int lastMax = 0;
        int max = 0;
       
        for (int n : A){
            if (n>N) {
                lastMax = max;
            } else {
                if (result[n-1]<lastMax) {
                    result[n-1]=lastMax;
                }
                result[n-1]++;    

                if (result[n-1]>max) {
                    max = result[n-1];
                }
            }       
            // System.out.println(Arrays.toString(result)+" "+n+" "+max+" "+lastMax);
        }     
        for (int i=0; i<result.length; i++) {
            if (result[i]<lastMax){
                result[i]=lastMax;    
            }
        }
        
        return result;
    }
}
```

