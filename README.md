# LeetCode
1. Rotate array by d elements

```Java

public class Main{

     public static void main(String[] args){
        int[] arr = {2, 4, 6, 8, 10, 12, 14, 16, 18, 20};
        
        int d = 3;
        
        int gcd = findGcd(arr.length, d);
        
        rotateArray(arr, d, gcd);
     
        for(int i = 0 ; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
     }
     
     public static int findGcd(int num1, int num2) {
         while (num1 != num2) {
        	if(num1 > num2)
                num1 = num1 - num2;
            else
                num2 = num2 - num1;
        }
        return num2;
     }
     
     public static void rotateArray(int[] arr, int d,  int gcd) {
         int  n = arr.length;
         int k,j,temp;
         for(int i = 0; i < gcd; i++) {
             temp = arr[i];
             j = i;
             while(true) {
                k = j + d;
                
                if(k >=  n) {
                    k = k - n;
                } 
                
                if(k == i) {
                   break;
                }
                
                arr[j] = arr[k];
                
                j = k;
             }
             arr[j] = temp;
             
         }
         
     }
}
```
