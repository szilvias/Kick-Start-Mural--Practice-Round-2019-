# Kick Start Problem: Mural (Practice Round 2019)
Click here to check the problem <https://codingcompetitions.withgoogle.com/kickstart/round/0000000000051060/0000000000058b89>

I first calculated the sum of the first n/2 elements in the array with even length (or the frist (n+1)/2 elements in the array with odd length).
Then push it back one element at a time, choose the largest sum as the final results.


```java
import java.util.Scanner;

public class Solution{
    public static void main(String[] args) { 
        Scanner input = new Scanner(System.in);        
        int T = input.nextInt();
        for (int ks = 1; ks <= T; ks++) {            
            int N = input.nextInt();            
            String digits = input.next();
            char[] digitss = digits.toCharArray();
            
            int temp = 0;            
            for(int i = 0; i<(N+1)/2; i++){
                temp = temp + Character.getNumericValue(digitss[i]);
            }            
            int ergebnis = temp;                        
            for(int j =0 ; j<(N+1)/2; j++){
                if((N+1)/2+j < N){
                temp = temp - Character.getNumericValue(digitss[j]) + Character.getNumericValue(digitss[(N+1)/2+j]);}
                ergebnis = Math.max(ergebnis, temp);            
            }
            System.out.println("Case #"+ ks + ": " + ergebnis);
        }
    }
}
```
