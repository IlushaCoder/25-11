[Problem]{https://www.codewars.com/kata/5803ee0ed5438edcc900008}
#My solution
public class Solution {
  public static long padovan(int n) {
    if(n==0)
      return 1;
    if(n==1)
      return 1;
    if(n==2)
      return 1;
    long pPrevPrev = 1, pPrev = 1, pCurr = 1, pNext = 1;
 
    for (int i=3; i<=n; i++)
    {
        pNext = pPrevPrev + pPrev;
        pPrevPrev = pPrev;
        pPrev = pCurr;
        pCurr = pNext;
    }
 
    return pNext;
  }
}
Favourite solution:
public class Solution {
  public static long padovan(int n) {
    var sequence = new long[n + 3];
    sequence[0] = 1;
    sequence[1] = 1;
    sequence[2] = 1;

    for (var i = 2; i < n; i++) {
      sequence[i + 1] = sequence[i - 1] + sequence[i - 2];
    }

    return sequence[n];
  }
}


