# C-
C#の内容をまとめていく

#メソッド、演算子まとめ

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

string[] split = str.Split(','); //文字列を区切り文字で分割して、文字列配列に格納する。区切り文字は複数指定可能。
string[] split2 = str.Split(new char[] { '+', '-', '=' }, 3); //第二引数に数値を指定すると戻り値の配列の要素数を制限できる。
string str = "Apple, Grape, Orahge";
string[] split = str.Split(new char[] ( ', ', ' ' ), StringSplitOptions.RemoveEmptyEntries); //文字列分割の際に、要素数がゼロになる要素が省かれる。
string[] split = str.Split(new string[] {","}, StringSplitOptions.None); //区切り文字に文字列を使用、戻り値の配列にからの要素が含まれていてもそのまま。

string str = " I have a pen ";
strinng trim = str.Trim(); // "I have a pen" 文字列の前後にある不要な空白を除去(Tabは消えない)
string trimStart = str.TrimStart(); // "I have a pen "　文字列の先頭の空白を除去(Tabは消えない)
string trimEnd = str.TrimEnd(); // " I have a pen"　文字列の末尾の空白を除去(Tabは消えない)

string str = "abcde";
int index1 = str.IndexOf('d'); //3
int index2 = str.IndexOf('z'); //-1
int index3 = str.IndexOf("cde"); //2
/* 見つからなかったら-1                          
 *第二引数に数値(startIndex)を指定することで、そこから検索が可能                              *
 *第三引数に数値(count)を指定すると、検索対象がstartIndex ~ countになる                       *
 *これらの後にStringComparision.OrdinalIgnoreCaseを指定すると、大文字小文字の区別なく検索できる*
 *ただし、この場合、検索文字は一文字でもstringでないといけない                                 */
 int lastIndex = str.LastIndexf('a'); //7 検索は後ろからだが、結果は先頭からのものと同じ
 
 

```


