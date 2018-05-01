# LeetCode刷题系列（二）：Unique Morse Code Words(804)

## 常规解法

```java
public int uniqueMorseRepresentations(String[] words) {
    String[] MORSE = new String[]{".-","-...","-.-.","-..",".","..-.","--.",
                    "....","..",".---","-.-",".-..","--","-.",
                    "---",".--.","--.-",".-.","...","-","..-",
                    "...-",".--","-..-","-.--","--.."};
    Set<String> seen = new HashSet();
    for (String word: words) {
        StringBuilder code = new StringBuilder();
        for (char c: word.toCharArray())
            code.append(MORSE[c - 'a']);
        seen.add(code.toString());
    }
    return seen.size();
}
```