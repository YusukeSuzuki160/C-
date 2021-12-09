# C#
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
```
#string.IsNullOrEmpty(string)
```
string.IsNullOrEmpty(str); //引数の文字列がnullもしくは空文字の時にtrueを返す
```
#str.ToUpper; str.ToLower
```
string strUpper = str.ToUpper; // 文字列を大文字変換
string strLower = str.ToLower; // 文字列を小文字変換
```
#string.Concat(string, string); str1 + str2;
```
string concat1 = string.Concat(str1, str2); //
string concat2 = str1 + str2; //どちらも文字列結合。string.Concatの引数は４つまで
```
#string.Join(string, string[])
```
string join = string.Join(":", strs); //string型配列に対して、区切り文字で文字列を連結。区切り無しなら、第一引数にstring.Emotyを指定
```
#str.Split(char or char[] or string[], int, StringSplitOptions)
```
string[] split = str.Split(','); //文字列を区切り文字で分割して、文字列配列に格納する。区切り文字は複数指定可能。
string[] split2 = str.Split(new char[] { '+', '-', '=' }, 3); //第二引数に数値を指定すると戻り値の配列の要素数を制限できる。
string str = "Apple, Grape, Orahge";
string[] split = str.Split(new char[] ( ', ', ' ' ), StringSplitOptions.RemoveEmptyEntries); //文字列分割の際に、要素数がゼロになる要素が省かれる。
string[] split = str.Split(new string[] {","}, StringSplitOptions.None); //区切り文字に文字列を使用、戻り値の配列にからの要素が含まれていてもそのまま。
```
#str.Trim(); str.TrimStart(); str.TrimEnd();
```
string str = " I have a pen ";
strinng trim = str.Trim(); // "I have a pen" 文字列の前後にある不要な空白を除去(Tabは消えない)
string trimStart = str.TrimStart(); // "I have a pen "　文字列の先頭の空白を除去(Tabは消えない)
string trimEnd = str.TrimEnd(); // " I have a pen"　文字列の末尾の空白を除去(Tabは消えない)
```
#str.IndexOf(char, int, int, StringComparision);
```
string str = "abcde";
int index1 = str.IndexOf('d'); //3
int index2 = str.IndexOf('z'); //-1
int index3 = str.IndexOf("cde"); //2
int index4 = str.IndexOf('a', index);
int index5 = str.IndexOf('a', 0, 3); //-1
int index6 = str.IndexOf("a", StringComparision.OrdinalIgnoreCase);
/* 見つからなかったら-1                          
 *第二引数に数値(startIndex)を指定することで、そこから検索が可能                              *
 *第三引数に数値(count)を指定すると、検索対象がstartIndex ~ countになる                       *
 *これらの後にStringComparision.OrdinalIgnoreCaseを指定すると、大文字小文字の区別なく検索できる*
 *ただし、この場合、検索文字は一文字でもstringでないといけない                                 */
int lastIndex = str.LastIndexf('a'); //7 検索は後ろからだが、結果は先頭からのものと同じ

string str = "I have a pen";
char[] chars = new char[] { 'a', 'h', 'p' };
int index1 = str.IndexOfAny(chars); //2
int index2 = str.IndexOfAny(chars, 5); //7
int index3 = str.IndexOfAny(chars, 5, 2); //-1 5文字目から2文字分を検索
/*string型の検索と、大文字小文字の区別のない検索はできない*/

int index1 = str.LastIndexOfAny(chars); //9
int index2 = str.LastIndexOfAny(chars, 5); //3
int index3 = str.LastIndexOfAny(chars, 5, 2); //-1
/*IndexOfAnyの後方検索版*/
```
#str.Contaions(string);
```
string str = "I have a pen";
bool contains1 = str.Contains("ve a"); //true
bool contains2 = str.Contains("apen"); //false
/*文字列に特定の文字列が含まれるかを判定する*/
```
#str.StartWith(string); str.Endwith(string);
```
string str = "I have a pen";
bool startWith1 = str.StartsWith("I h"); //true
bool startWith2 = str.StartsWith("have"); //false

bool endsWith1 = str.EndsWith("en"); //true
bool endsWith2 = str.EndsWith("a"); //false
/*文字列が特定の文字列で開始する(終了する)かを判定する。                                      *
 *第二引数にStringComparision.OrdinalIgnoreCaseを指定して、大文字小文字の区別をしないことも可能*/
```
#str.Equal(string); string.Equal(string, string); str1 == str2;
```
string str = "Pencil";
bool op = str == "Pensil"; //true
bool equals = str.Equals("Pensil"); //true
/*いわゆる等価演算子のオーバーロード*
 *大文字小文字を区別しないことも可能*
 *nullチェックはできない         */
string str = null;
bool equals = string.Equals(str, null); //true
/*静的メソッドならばnullチェック可能*/
```
#str.Substring(int, int);
```
string str = "I have a pen";
string subString1 = str.Substring(7); //開始位置から末尾まで取得
string subString2 = str.Substring(7, 3); //開始位置からn文字取得
```
#str.Remove(int, int);
```
string str = "I have a pen";
string remove1 = str.Remove(6); //6文字目から末尾まで削除
string remove2 = str.Remove(6, 3); //6文字目から3文字を削除
```
#str.Replace(string, string);
```
string replace1 = str.Replace("a pen", "an apple");
string replace2 = str.Replace(" ", string.Empty); //半角スペースをすべて削除
```
#str.PadLeft(int, char); str.PadRight(int, char);
```
string str1 = "1";
string str2 = "20";
str1 = str1.PadLeft(4); //指定の文字数に達するまで左側を空白で埋める。
str2 = str2.PadRight(4); //右端を空白で埋める。

string str1 = "1";
string str2 = "20";
str1 = str1.PadLeft(4, '0'); //0001
str2 = str2.PadLeft(4, '*'); //20**
```
#string.Compare(string, string);
```
string str1 = "Apple";
string str2 = "Orange";
string str3 = "Grape";

int compare1 = string.Compare(str1, str2); //-1
int compare2 = string.Compare(str2, str3); //-1
int compare3 = stirng.Compare(str1, str1); //0
/*２つの文字列を比較し、並べ替えに使用する順序を整数で返す。第一引数のほうが辞書順で先なら-1、あとなら1、同一なら0を返す。* 
 *大文字小文字を区別しないことも可能                                                                        */
```
string.Formatは別途記載

参考 https://programming.pc-note.net/csharp/string_method.html 


