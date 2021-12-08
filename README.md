# C-
C#の内容をまとめていく

#標準入出力
```
Console.ReadLine(); //標準入力から一行読み取り
Console.WriteLine(x); //標準出力へxを出力
Console.WriteLine($"{x}, {y}, {z}") //{}で囲むことで出力の形式を自由にできる
```
#演算子
```
(bool) ? a : b; //boolがtrueならaを、falseならbを返す
```
#Stringクラス
```
string s1; //宣言
char[] chars = new char[] {'a', 'b', 'c7', 'd', 'e', 'f', 'g' }
string s2 = new string(chars); //char方配列をstringに変換して生成
string s3 = new string(chars, 1, 3); //１文字目から３文字目までをstring型に変換して代入
string s4 = new string('a', 10); //文字'a'を１０文字代入
string s3 = "abcdefg";　//初期化
string.IsNullOrEmpty(str); //引数の文字列がnullもしくは空文字の時にtrueを返す
string strUpper = str.ToUpper; // 文字列を大文字変換
string strLower = str.ToLower; // 文字列を小文字変換
string concat1 = string.Concat(str1, str2); //
string concat2 = str1 + str2; //どちらも文字列結合。string.Concatの引数は４つまで
string join = string.Join(":", strs); //string型配列に対して、区切り文字で文字列を連結。区切り無しなら、第一引数にstring.Emotyを指定
```


