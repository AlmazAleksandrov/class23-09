### Task 8kyu:

Write a method, that will get an integer array as parameter and will process every number from this array.
Return a new array with processing every number of the input-array like this:
If the number has an integer square root, take this, otherwise square the number.

[Task link](https://www.codewars.com/kata/57f6ad55cca6e045d2000627/train/java)

#### Solution:
```
public class Kata
{
  public static int[] squareOrSquareRoot(int[] array)
  {
    int[] array_1 = new int[array.length]; 
    for (int i = 0; i < array.length; i++){
      if (Math.sqrt(array[i]) % 1 == 0){
        array_1[i] = (int) Math.sqrt (array[i]);
      }
      else{
        array_1[i] = (int) Math.pow (array[i], 2);
      }                       
    }
    return array_1;
  }
}
```

#### Fav solution:
```
import java.util.Arrays;
public class Kata {
  public static int[] squareOrSquareRoot(int[] array) {
    return Arrays.stream(array)
          .map(i -> {
            var sqrt = Math.sqrt(i);
            return sqrt % 1 == 0 ? (int) sqrt : i * i;          
          }) 
          .toArray();        
  }
}
```

#### Comment:
Used the function, instead of counting manually. But the code looks more understandable.


### Task 6kyu:

Write simple .camelCase method (camel_case function in PHP,
CamelCase in C# or camelCase in Java) for strings. 
All words must have their first letter capitalized without spaces.

[Task link](https://www.codewars.com/kata/587731fda577b3d1b0001196/java)

#### Solution:
```
public class Solution {
    public static String camelCase(String str) {
        String[] str_1 = str.split(" ");
        String result = "";
        for(int i = 0; i < str_1.length; i++)
        {
           if(str_1[i].length() > 1){
              result += str_1[i].substring(0, 1).toUpperCase() + 
              str_1[i].substring(1).toLowerCase();
          }
          else{
            result += str_1[i].substring(0).toUpperCase();
          }
        }
        return result;
    }
}
```

#### Fav solution:
```
import java.lang.Object;
import org.apache.commons.lang3.text.WordUtils;

public class Solution {
    public static String camelCase(String str) {
        str = WordUtils.capitalize(str);
        str = str.replaceAll(" ","");
        return str;
    }

}
```

#### Comment:
There was such a suitable function that made the task easier.
