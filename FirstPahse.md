#CSHARP-Basic
### 1. Local Değişkenler Oluşturma
- `var` ile tanımlanan değişkenler **kesinlikle** başlangıç değeri ile initialize edilmelidir.
- Örnek:
```csharp
var localMessage = "Hello Locals!";  // Doğru
var localMessage;                    // Hatalı, bu şekilde bırakılamaz
```
### 2. `Console.WriteLine` ve Kaçış Karakterleri
- Yeni satır için: `\n`
- Tab boşluğu için: `\t`
Örnek çıktı:
```csharp
Console.WriteLine("Hello\nWorld!");  //  
// Output:  
// Hello  
// World!

Console.WriteLine("Hello\tWorld!");  
// Output:  
// Hello   World!
```
### 3. Verbatim String (Literal String)
- Uzun dosya yolu ya da çok satırlı stringler için `@` işareti kullanılır.    
- Böylece kaçış karakterlerine gerek kalmaz.
Örnek:

```csharp
Console.WriteLine(@"    c:\source\repos
(this is verbatim string)");
```
### 4. String Interpolation (String Yerine Koyma)
- `$` işareti ile string içine doğrudan değişken ekleyebilirsin.
Örnek:

```csharp
string greeting = "Hello";
string firstName = "Bob";
string message = $"{greeting} {firstName}!";
Console.WriteLine(message);  // Output: Hello Bob!
```
### 5. Verbatim String + String Interpolation Birlikte Kullanımı
- Hem `@` hem de `$` birlikte kullanılabilir.
Örnek:

```csharp
string projectName = "First-Project";
Console.WriteLine($@"C:\Output\{projectName}\Data");  
// Output: C:\Output\First-Project\Data
```
### 6. String ve Sayıların Toplanması (Concatenation)
- Parantez kullanılmazsa, toplama işlemi string olarak algılanır ve sonuç beklenmedik olur.

Örnek:

```csharp
string firstName = "Bob";
int widgetsSold = 7;

Console.WriteLine(firstName + " sold " + widgetsSold + 7 + " widgets.");  
// Output: Bob sold 77 widgets. (Yanlış)

Console.WriteLine(firstName + " sold " + (widgetsSold + 7) + " widgets.");  
// Output: Bob sold 14 widgets. (Doğru)
```
- **Parantez** kullanımı sayısal toplamanın doğru yapılmasını sağlar.

### 7. Sayı Türleri Arasında Doğru Bölme İşlemi
- Farklı türlerdeki sayılar (`int`, `decimal`) doğrudan bölünemez.
- Bu durum hata verir veya beklenmedik sonuçlar oluşturur.

Hatalı kodlar:

```csharp
int decimalQuotient = 7 / 5.0m;  
int decimalQuotient = 7.0m / 5;  
int decimalQuotient = 7.0m / 5.0m;  
decimal decimalQuotient = 7 / 5;
```

Doğru kullanım:

```csharp
int first = 7;
int second = 5;
decimal quotient = (decimal)first / (decimal)second;
Console.WriteLine(quotient);  // Output: 1.4
```

- Burada **explicit cast** (açık dönüşüm) yaparak doğru sonuç alıyoruz.
### 8. Increment (Arttırma) Operatörleri

- `value++` (Post-increment): önce değeri kullan, sonra artır.
- `++value` (Pre-increment): önce artır, sonra kullan.
Örnek:

```csharp
int value = 1;
value++;
Console.WriteLine("First: " + value);      // First: 2
Console.WriteLine($"Second: {value++}");    // Second: 2  (Değeri kullanır, sonra artırır)
Console.WriteLine("Third: " + value);       // Third: 3
Console.WriteLine("Fourth: " + (++value));  // Fourth: 4  (Önce artırır, sonra kullanır)
```
