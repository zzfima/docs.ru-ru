---
title: "Кодировка символов в .NET"
description: "Кодировка символов в .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bce54e41-e9dc-493a-8988-1cbadc340fe8
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: e72540726bdd1b3624064c7388e58d80320c5831

---

# <a name="character-encoding-in-net"></a>Кодировка символов в .NET

Символы — это абстрактные сущности, которые могут быть представлены различными способами. Кодировка — это система, где с каждым символом поддерживаемого набора символов сопоставляется значение, представляющее этот символ. Например, азбука Морзе — это кодировка, в которой каждому символу латинского алфавита соответствует набор точек и тире, которые можно передавать с помощью телеграфа. Компьютерная кодировка — это система, где с каждым символом поддерживаемого набора символов сопоставлено числовое значение, представляющее этот символ. Кодировка состоит из двух компонентов:

* кодировщик, преобразующий последовательность символов в последовательность числовых значений (байтов);

* декодер, преобразующий последовательность байтов в последовательность символов.

Кодировка описывает правила, по которым работают кодировщик и декодер. Например, класс [UTF8Encoding](xref:System.Text.UTF8Encoding) описывает правила кодирования и декодирования для формата UTF-8, в котором используется от одного до четырех байтов для представления одного символа Юникода. В процессе кодирования и декодирования также может выполняться проверка. Например, класс [UnicodeEncoding](xref:System.Text.UnicodeEncoding) предназначен для проверки допустимости пар, составляемых всеми символами-заместителями. (Пара символов-заместителей состоит из символа с кодовой точкой в диапазоне от U+D800 до U+DBFF и символа с кодовой точкой в диапазоне от U+DC00 до U+DFFF.) Резервная стратегия определяет, как кодировщик обрабатывает недопустимые символы или как декодер обрабатывает недопустимые байты. 

> [!WARNING]
> Классы кодировок .NET позволяют хранить и преобразовывать символьные данные. Их не следует использовать для хранения двоичных данных в строковом виде. В зависимости от используемой кодировки преобразование двоичных данных в строковый формат с использованием классов кодировок может привести к неожиданному результату и неточным или поврежденным данным. Для преобразования двоичных данных в строковый формат используйте метод [Convert.ToBase64String](xref:System.Convert.ToBase64String(System.Byte[])). 
 
Платформа .NET использует кодировку UTF-16 (представленную классом [UnicodeEncoding](xref:System.Text.UnicodeEncoding)) для представления символов и строк. В приложениях, предназначенных для среды CLR, кодировщики используются для сопоставления представлений символов Юникода, поддерживаемых средой CLR, с другими схемами кодирования. Декодеры служат для сопоставления символов различных кодировок с Юникодом.

В этом разделе:

* [Кодировки в .NET](#encodings-in-net)

* [Выбор класса кодировки](#selecting-an-encoding-class)

* [Использование объекта кодировки](#using-an-encoding-object)

* [Выбор резервной стратегии](#choosing-a-fallback-strategy)

* [Реализация пользовательской резервной стратегии](#implementing-a-custom-fallback-strategy)

## <a name="encodings-in-net"></a>Кодировки в .NET

Все классы кодировок в .NET наследуют от класса [System.Text.Encoding](xref:System.Text.Encoding) — абстрактного класса, определяющего общую для всех кодировок функциональность. Для доступа к отдельным объектам кодировок, реализованным в .NET, можно сделать следующее:

* Использовать статические свойства класса [Encoding](xref:System.Text.Encoding), возвращающие объекты, которые представляют стандартные кодировки, доступные в .NET (ASCII, UTF-7, UTF-8, UTF-16 и UTF-32). Например, свойство [Encoding.Unicode](xref:System.Text.Encoding.Unicode) возвращает объект [UnicodeEncoding](xref:System.Text.UnicodeEncoding). Каждый объект использует резервную стратегию замены для обработки строк, которые он не может закодировать, и байтов, которые не может декодировать. (Подробнее см. в разделе [Стратегия замены](#replacement-fallback).)

* Вызвать конструктор класса кодировки. Таким образом могут быть созданы объекты для кодировок ASCII, UTF-7, UTF-8, UTF-16 и UTF-32. По умолчанию каждый объект использует резервную стратегию замены для обработки строк, которые он не может закодировать, и байтов, которые он не может декодировать, но вы можете указать, чтобы вместо этого создавалось исключение. (Подробнее см. в разделах [Стратегия замены](#replacement-fallback) и [Стратегия исключения](#exception-fallback).)

* Вызвать конструктор [Encoding.Encoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) и передать ему целое число, представляющее кодировку. Объекты стандартных кодировок используют резервные стратегии замены, а объекты кодовых страниц и двухбайтовых кодировок (DBCS) используют резервную стратегию наилучшего соответствия для обработки строк, которые не удается закодировать, или байтов, которые не удается декодировать. (Подробнее см. в разделе [Стратегия наилучшего соответствия](#best-fit-fallback).)

* Вызвать метод [Encoding.GetEncoding](xref:System.Text.Encoding.GetEncoding(System.Int32)), возвращающий любую стандартную кодировку, кодовую страницу или кодировку DBCS, доступную в .NET. Перегрузки позволяют задать резервный объект как для кодировщика, так и для декодера.

> [!NOTE]
> В стандарте Юникода каждому символу в каждом поддерживаемом символьном наборе присваивается кодовая точка (номер) и имя. Например, символ "A" представляется кодовой точкой U+0041 и именем LATIN CAPITAL LETTER A. Кодировки UTF определяют способы кодирования кодовой точки в виде последовательности из одного или нескольких байтов. Схема кодировки Юникод упрощает разработку международных приложений, так как позволяет представлять символы любых наборов символов в единой кодировке. Разработчикам приложений больше не нужно сохранять данные о схеме кодировки, которая использовалась для представления символов конкретного языка или системы письма. Передача данных между системами, использующими различные языки, может происходить без искажений.
>
>  Платформа .NET поддерживает три кодировки, определенные стандартом Юникод: UTF-8, UTF-16 и UTF-32. Дополнительные сведения см. в описании стандарта Юникод на домашней странице [Юникода](http://www.unicode.org/).
 
Платформа .NET поддерживает системы кодирования символов, перечисленные в таблице ниже.

Кодировка | Класс | Описание | Преимущества и недостатки
-------- | ----- | ----------- | ------------------------ 
ASCII | [ASCIIEncoding](xref:System.Text.ASCIIEncoding) | Кодирует ограниченный диапазон символов, используя семь младших битов байта. | Так как эта кодировка поддерживает только значения символов от U+0000 до U+007F, то в большинстве случаев она не отвечает требованиям международных приложений.
UTF-7 | [UTF7Encoding](xref:System.Text.UTF7Encoding) | Представляет символы в виде последовательностей 7-разрядных символов ASCII. Символы Юникода, не относящиеся к ASCII, представляются в виде escape-последовательности символов ASCII. | UTF-7 поддерживает протоколы, например протоколы электронной почты и групп новостей. Однако формат UTF-7 недостаточно безопасен и надежен. В некоторых случаях изменение одного бита может привести к существенному изменению интерпретации всей строки UTF-7. В других случаях для кодировки одного и того же текста могут использоваться разные строки UTF-7. В последовательностях, содержащих отличные от ASCII символы, формат UTF-7 требует больше места, чем UTF-8, а кодирование и декодирование выполняются медленнее. Поэтому по возможности лучше использовать UTF-8 вместо UTF-7.
UTF-8 | [UTF8Encoding](xref:System.Text.UTF8Encoding) | Представляет каждую кодовую точку Юникода в виде последовательности от одного до четырех байтов. | UTF-8 поддерживает 8-разрядный размер данных и хорошо работает со многими операционными системами. Для диапазона символов ASCII кодировка UTF-8 идентична кодировке ASCII и предоставляет более широкий набор символов. Однако для китайской, японской и корейской письменности UTF-8 может потребовать три байта для каждого символа, что может привести к большему объему данных по сравнению с UTF-16. Обратите внимание, что иногда увеличение размера данных для китайской, японской и корейской письменности объясняется объемом данных ASCII, например тегами HTML.
UTF-16 | [UnicodeEncoding](xref:System.Text.UnicodeEncoding) | Представляет каждую кодовую точку Юникода в виде последовательности одного или двух 16-разрядных целых чисел. Наиболее распространенные символы Юникода требуют только одной кодовой точки UTF-16, хотя дополнительные символы Юникода (U+10000 и далее) требуют двух замещающих кодовых точек UTF-16. Поддерживаются оба порядка байтов: прямой и обратный. | Кодировка UTF-16 используется средой CLR для представления значений Char и String, а операционной системой Windows — для представления значений WCHAR.
UTF-32 | [UTF32Encoding](xref:System.Text.UTF32Encoding) | Представляет каждую кодовую точку Юникода в виде 32-разрядного целого числа. Поддерживаются оба порядка байтов: прямой и обратный. | Кодировка UTF-32 используется в случае, когда приложению требуется избежать поведения замещающей кодовой точки кодировки UTF-16 в операционных системах, в которых закодированное пространство имеет большое значение. Для кодирования отдельных отображаемых глифов может использоваться несколько символов UTF-32.

Эти кодировки позволяют работать с символами Юникода, а также с кодировками, которые часто используются в приложениях прежних версий. Кроме того, можно создать настраиваемую кодировку, определив класс, производный от [Encoding](xref:System.Text.Encoding), и переопределив его члены.

> [!NOTE]
> По умолчанию .NET Core не предоставляет доступ к кодировкам кодовых страниц, кроме кодовой страницы 28591 и кодировок Юникода, например UTF-8 и UTF-16. Однако вы можете добавить в свое приложение кодировки кодовых страниц из стандартных приложений Windows, ориентированных на .NET Framework. Подробнее см. в разделе [EncodingProvider](xref:System.Text.EncodingProvider). 

## <a name="selecting-an-encoding-class"></a>Выбор класса кодировки

Если у вас есть возможность выбрать кодировку для использования в приложении, следует использовать Юникод, предпочтительно [UTF8Encoding](xref:System.Text.UTF8Encoding) или [UnicodeEncoding](xref:System.Text.UnicodeEncoding). (Платформа .NET также поддерживает третью кодировку — Юникод [UTF32Encoding](xref:System.Text.UTF32Encoding).) 

Если вы планируете использовать кодировку ASCII ([ASCIIEncoding](xref:System.Text.ASCIIEncoding)), выберите вместо нее [UTF8Encoding](xref:System.Text.UTF8Encoding). Эти две кодировки идентичны для набора символов ASCII, но [UTF8Encoding](xref:System.Text.UTF8Encoding) имеет указанные ниже преимущества. 

* Она может представлять любой символ Юникода, тогда как [ASCIIEncoding](xref:System.Text.ASCIIEncoding) поддерживает только символы Юникода в диапазоне от U+0000 до U+007F.

* Она обеспечивает обнаружение ошибок и более высокий уровень безопасности.

* Она настроена для максимально быстрой работы и должна быть быстрее любых других кодировок. Даже для содержимого, имеющего только формат ASCII, выполнение операций с помощью [UTF8Encoding](xref:System.Text.UTF8Encoding) происходит быстрее, чем с помощью [ASCIIEncoding](xref:System.Text.ASCIIEncoding).

Кодировку [ASCIIEncoding](xref:System.Text.ASCIIEncoding) рекомендуется использовать только для приложений прежних версий. Однако даже для приложений прежних версий [UTF8Encoding](xref:System.Text.UTF8Encoding) может быть предпочтительнее по указанным ниже причинам (при параметрах по умолчанию).

* Если содержимое приложения включает символы не только в формате ASCII, при кодировании с помощью [ASCIIEncoding](xref:System.Text.ASCIIEncoding) каждый символ, не относящийся к ASCII, кодируется как знак вопроса (?). При последующем декодировании эти данные утрачиваются.


* Если содержимое приложения включает символы не только в формате ASCII, при кодировании с помощью [UTF8Encoding](xref:System.Text.UTF8Encoding) представление символов в формате ASCII дает непригодный для чтения результат. Однако при последующем декодировании данных с помощью декодера UTF-8 обработка данных выполняется успешно.

В веб-приложении символы, отправленные клиенту в ответ на веб-запрос, должны отражать кодировку, используемую в клиенте. Как правило, требуется задать для свойства [HttpResponse.ContentEncoding](xref:System.Net.HttpResponseHeader.ContentEncoding) значение, возвращаемое свойством [HttpRequestHeader.ContentEncoding](xref:System.Net.HttpRequestHeader.ContentEncoding), для отображения текста в той кодировке, которую ожидает пользователь.

## <a name="using-an-encoding-object"></a>Использование объекта кодировки

Кодировщик преобразует строку символов (чаще всего символов Юникода) в их числовой (байтовый) эквивалент. Например, кодировщик ASCII можно использовать для преобразования символов Юникода в ASCII, чтобы они могли отображаться на консоли. Чтобы выполнить преобразование, вызовите метод [Encoding.GetBytes](xref:System.Text.Encoding.GetBytes(System.Char[])). Если перед выполнением кодирования нужно определить, сколько байтов потребуется для хранения закодированных символов, можно вызвать метод [GetByteCount](xref:System.Text.Encoding.GetByteCount(System.Char[])).

В примере ниже один массив байтов используется для кодирования строк в двух отдельных операциях. Имеется индекс, указывающий начальную позицию в массиве байтов для следующего набора байтов, закодированных с использованием ASCII. Вызывается метод [ASCIIEncoding.GetByteCount(String)](xref:System.Text.ASCIIEncoding.GetByteCount(System.String)) для проверки того, что массив байтов достаточно велик для хранения закодированной строки. Затем вызывается метод [ASCIIEncoding.GetBytes(String, Int32, Int32, Byte[], Int32)](xref:System.Text.ASCIIEncoding.GetBytes(System.Char[],System.Int32,System.Int32,System.Byte[],System.Int32)) для кодирования символов в строке.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings= { "This is the first sentence. ", 
                          "This is the second sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;

      // Create array of adequate size.
      byte[] bytes = new byte[49];
      // Create index for current position of array.
      int index = 0;

      Console.WriteLine("Strings to encode:");
      foreach (var stringValue in strings) {
         Console.WriteLine("   {0}", stringValue);

         int count = asciiEncoding.GetByteCount(stringValue);
         if (count + index >=  bytes.Length)
            Array.Resize(ref bytes, bytes.Length + 50);

         int written = asciiEncoding.GetBytes(stringValue, 0, 
                                              stringValue.Length, 
                                              bytes, index);    

         index = index + written; 
      } 
      Console.WriteLine("\nEncoded bytes:");
      Console.WriteLine("{0}", ShowByteValues(bytes, index));
      Console.WriteLine();

      // Decode Unicode byte array to a string.
      string newString = asciiEncoding.GetString(bytes, 0, index);
      Console.WriteLine("Decoded: {0}", newString);
   }

   private static string ShowByteValues(byte[] bytes, int last ) 
   {
      string returnString = "   ";
      for (int ctr = 0; ctr <= last - 1; ctr++) {
         if (ctr % 20 == 0)
            returnString += "\n   ";
         returnString += String.Format("{0:X2} ", bytes[ctr]);
      }
      return returnString;
   }
}
// The example displays the following output:
//       Strings to encode:
//          This is the first sentence.
//          This is the second sentence.
//       
//       Encoded bytes:
//       
//          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
//          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
//       
//       Decoded: This is the first sentence. This is the second sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII

      ' Create array of adequate size.
      Dim bytes(50) As Byte
      ' Create index for current position of array.
      Dim index As Integer = 0

      Console.WriteLine("Strings to encode:")
      For Each stringValue In strings
         Console.WriteLine("   {0}", stringValue)

         Dim count As Integer = asciiEncoding.GetByteCount(stringValue)
         If count + index >=  bytes.Length Then
            Array.Resize(bytes, bytes.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetBytes(stringValue, 0, 
                                                         stringValue.Length, 
                                                         bytes, index)    

         index = index + written 
      Next 
      Console.WriteLine()
      Console.WriteLine("Encoded bytes:")
      Console.WriteLine("{0}", ShowByteValues(bytes, index))
      Console.WriteLine()

      ' Decode Unicode byte array to a string.
      Dim newString As String = asciiEncoding.GetString(bytes, 0, index)
      Console.WriteLine("Decoded: {0}", newString)
   End Sub

   Private Function ShowByteValues(bytes As Byte(), last As Integer) As String
      Dim returnString As String = "   "
      For ctr As Integer = 0 To last - 1
         If ctr Mod 20 = 0 Then returnString += vbCrLf + "   "
         returnString += String.Format("{0:X2} ", bytes(ctr))
      Next
      Return returnString
   End Function
End Module
' The example displays the following output:
'       Strings to encode:
'          This is the first sentence.
'          This is the second sentence.
'       
'       Encoded bytes:
'       
'          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
'          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
'       
'       Decoded: This is the first sentence. This is the second sentence.
```

Декодер преобразует массив байтов, отражающий конкретную кодировку символов, в набор символов в массиве символов или в строке. Чтобы декодировать массив байтов в массив символов, вызовите метод [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])). Чтобы декодировать массив байтов в строку, вызовите метод [GetString](xref:System.Text.Encoding.GetString(System.Byte[])). Если перед декодированием нужно определить, сколько символов требуется для хранения раскодированных байтов, можно вызвать метод [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])).

В примере ниже три строки кодируются, а затем декодируются в один массив символов. Имеется индекс, указывающий начальную позицию в массиве символов для следующего набора декодированных символов. Вызывается метод [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])) для проверки того, что массив символов достаточно велик для хранения всех декодированных символов. Затем вызывается метод [ASCIIEncoding.GetChars(Byte[], Int32, Int32, Char[], Int32)](xref:System.Text.ASCIIEncoding.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) для декодирования массива байтов.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings = { "This is the first sentence. ", 
                           "This is the second sentence. ",
                           "This is the third sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;
      // Array to hold encoded bytes.
      byte[] bytes;
      // Array to hold decoded characters.
      char[] chars = new char[50];
      // Create index for current position of character array.
      int index = 0;     

      foreach (var stringValue in strings) {
         Console.WriteLine("String to Encode: {0}", stringValue);
         // Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue);
         // Display the encoded bytes.
         Console.Write("Encoded bytes: ");
         for (int ctr = 0; ctr < bytes.Length; ctr++)
            Console.Write(" {0}{1:X2}", 
                          ctr % 20 == 0 ? Environment.NewLine : "", 
                          bytes[ctr]);
         Console.WriteLine();

         // Decode the bytes to a single character array.
         int count = asciiEncoding.GetCharCount(bytes);
         if (count + index >=  chars.Length)
            Array.Resize(ref chars, chars.Length + 50);

         int written = asciiEncoding.GetChars(bytes, 0, 
                                              bytes.Length, 
                                              chars, index);              
         index = index + written;
         Console.WriteLine();       
      }

      // Instantiate a single string containing the characters.
      string decodedString = new string(chars, 0, index - 1);
      Console.WriteLine("Decoded string: ");
      Console.WriteLine(decodedString);
   }
}
// The example displays the following output:
//    String to Encode: This is the first sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the second sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
//    65 6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the third sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    Decoded string:
//    This is the first sentence. This is the second sentence. This is the third sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. ",
                                  "This is the third sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII
      ' Array to hold encoded bytes.
      Dim bytes() As Byte
      ' Array to hold decoded characters.
      Dim chars(50) As Char
      ' Create index for current position of character array.
      Dim index As Integer     

      For Each stringValue In strings
         Console.WriteLine("String to Encode: {0}", stringValue)
         ' Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue)
         ' Display the encoded bytes.
         Console.Write("Encoded bytes: ")
         For ctr As Integer = 0 To bytes.Length - 1
            Console.Write(" {0}{1:X2}", If(ctr Mod 20 = 0, vbCrLf, ""), 
                                        bytes(ctr))
         Next         
         Console.WriteLine()

         ' Decode the bytes to a single character array.
         Dim count As Integer = asciiEncoding.GetCharCount(bytes)
         If count + index >=  chars.Length Then
            Array.Resize(chars, chars.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetChars(bytes, 0, 
                                                         bytes.Length, 
                                                         chars, index)              
         index = index + written
         Console.WriteLine()       
      Next

      ' Instantiate a single string containing the characters.
      Dim decodedString As New String(chars, 0, index - 1)
      Console.WriteLine("Decoded string: ")
      Console.WriteLine(decodedString)
   End Sub
End Module
' The example displays the following output:
'    String to Encode: This is the first sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the second sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
'    65 6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the third sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    Decoded string:
'    This is the first sentence. This is the second sentence. This is the third sentence.
```

Методы кодирования и декодирования класса, производного от класса [Encoding](xref:System.Text.Encoding), предназначены для работы с полным набором данных. Это значит, что все данные, подлежащие кодированию или декодированию, предоставляются в одном вызове метода. Однако в некоторых случаях данные предоставляются в потоке, тогда данные для кодирования и декодирования можно получить только с помощью нескольких операций чтения. В таком случае необходимо, чтобы операция кодирования или декодирования "помнила" сохраненное после предыдущего вызова состояние. Методы классов, производных от [Encoder](xref:System.Text.Encoder) и [Decoder](xref:System.Text.Decoder), могут обрабатывать операции кодирования и декодирования, охватывающие несколько вызовов методов.

Объект [Encoder](xref:System.Text.Encoder) для конкретной кодировки доступен в ее свойстве [Encoding.GetEncoder](xref:System.Text.Encoding.GetEncoder). Объект [Decoder](xref:System.Text.Decoder) для конкретной кодировки доступен в ее свойстве [Encoding.GetDecoder](xref:System.Text.Encoding.GetDecoder). Что касается операций декодирования, обратите внимание, что классы, производные от [Decoder](xref:System.Text.Decoder), включают метод [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)), но не имеют метода, соответствующего [Encoding.GetString](xref:System.Text.Encoding.GetString(System.Byte[])).

В примере ниже показано различие между использованием методов [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) и [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) для декодирования массива байтов Юникода. В этом примере строка, содержащая несколько символов Юникода, кодируется в файл, а затем два метода декодирования используются для декодирования по десять байтов за раз. Так как замещающая пара оказывается в десятом и одиннадцатом байтах, она декодируется в отдельных вызовах метода. Как видно из выходных данных, метод [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) не может правильно декодировать байты и заменяет их символом U+FFFD (замещающим символом). С другой стороны, метод [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) может успешно декодировать массив байтов для получения исходной строки.

```csharp
using System;
using System.IO;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Use default replacement fallback for invalid encoding.
      UnicodeEncoding enc = new UnicodeEncoding(true, false, false);

      // Define a string with various Unicode characters.
      string str1 = "AB YZ 19 \uD800\udc05 \u00e4"; 
      str1 += "Unicode characters. \u00a9 \u010C s \u0062\u0308"; 
      Console.WriteLine("Created original string...\n");

      // Convert string to byte array.                     
      byte[] bytes = enc.GetBytes(str1);

      FileStream fs = File.Create(@".\characters.bin");
      BinaryWriter bw = new BinaryWriter(fs);
      bw.Write(bytes);
      bw.Close();

      // Read bytes from file.
      FileStream fsIn = File.OpenRead(@".\characters.bin");
      BinaryReader br = new BinaryReader(fsIn);

      const int count = 10;            // Number of bytes to read at a time. 
      byte[] bytesRead = new byte[10]; // Buffer (byte array).
      int read;                        // Number of bytes actually read. 
      string str2 = String.Empty;      // Decoded string.

      // Try using Encoding object for all operations.
      do { 
         read = br.Read(bytesRead, 0, count);
         str2 += enc.GetString(bytesRead, 0, read); 
      } while (read == count);
      br.Close();
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...");
      CompareForEquality(str1, str2);
      Console.WriteLine();

      // Use Decoder for all operations.
      fsIn = File.OpenRead(@".\characters.bin");
      br = new BinaryReader(fsIn);
      Decoder decoder = enc.GetDecoder();
      char[] chars = new char[50];
      int index = 0;                   // Next character to write in array.
      int written = 0;                 // Number of chars written to array.
      do { 
         read = br.Read(bytesRead, 0, count);
         if (index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length) 
            Array.Resize(ref chars, chars.Length + 50);

         written = decoder.GetChars(bytesRead, 0, read, chars, index);
         index += written;                          
      } while (read == count);
      br.Close();            
      // Instantiate a string with the decoded characters.
      string str3 = new String(chars, 0, index); 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...");
      CompareForEquality(str1, str3); 
   }

   private static void CompareForEquality(string original, string decoded)
   {
      bool result = original.Equals(decoded);
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal));
      if (! result) {
         Console.WriteLine("Code points in original string:");
         foreach (var ch in original)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();

         Console.WriteLine("Code points in decoded string:");
         foreach (var ch in decoded)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    Created original string...
//    
//    Decoded string using UnicodeEncoding.GetString()...
//    original = decoded: False
//    Code points in original string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    Code points in decoded string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    
//    Decoded string using UnicodeEncoding.Decoder.GetString()...
//    original = decoded: True
```

```vb
Imports System.IO
Imports System.Text

Module Example
   Public Sub Main()
      ' Use default replacement fallback for invalid encoding.
      Dim enc As New UnicodeEncoding(True, False, False)

      ' Define a string with various Unicode characters.
      Dim str1 As String = String.Format("AB YZ 19 {0}{1} {2}", 
                                         ChrW(&hD800), ChrW(&hDC05), ChrW(&h00e4))
      str1 += String.Format("Unicode characters. {0} {1} s {2}{3}", 
                            ChrW(&h00a9), ChrW(&h010C), ChrW(&h0062), ChrW(&h0308))
      Console.WriteLine("Created original string...")
      Console.WriteLine()

      ' Convert string to byte array.                     
      Dim bytes() As Byte = enc.GetBytes(str1)

      Dim fs As FileStream = File.Create(".\characters.bin")
      Dim bw As New BinaryWriter(fs)
      bw.Write(bytes)
      bw.Close()

      ' Read bytes from file.
      Dim fsIn As FileStream = File.OpenRead(".\characters.bin")
      Dim br As New BinaryReader(fsIn)

      Const count As Integer = 10      ' Number of bytes to read at a time. 
      Dim bytesRead(9) As Byte         ' Buffer (byte array).
      Dim read As Integer              ' Number of bytes actually read. 
      Dim str2 As String = ""          ' Decoded string.

      ' Try using Encoding object for all operations.
      Do 
         read = br.Read(bytesRead, 0, count)
         str2 += enc.GetString(bytesRead, 0, read) 
      Loop While read = count
      br.Close()
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...")
      CompareForEquality(str1, str2)
      Console.WriteLine()

      ' Use Decoder for all operations.
      fsIn = File.OpenRead(".\characters.bin")
      br = New BinaryReader(fsIn)
      Dim decoder As Decoder = enc.GetDecoder()
      Dim chars(50) As Char
      Dim index As Integer = 0         ' Next character to write in array.
      Dim written As Integer = 0       ' Number of chars written to array.
      Do 
         read = br.Read(bytesRead, 0, count)
         If index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length Then 
            Array.Resize(chars, chars.Length + 50)
         End If   
         written = decoder.GetChars(bytesRead, 0, read, chars, index)
         index += written                          
      Loop While read = count
      br.Close()            
      ' Instantiate a string with the decoded characters.
      Dim str3 As New String(chars, 0, index) 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...")
      CompareForEquality(str1, str3) 
   End Sub

   Private Sub CompareForEquality(original As String, decoded As String)
      Dim result As Boolean = original.Equals(decoded)
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal))
      If Not result Then
         Console.WriteLine("Code points in original string:")
         For Each ch In original
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()

         Console.WriteLine("Code points in decoded string:")
         For Each ch In decoded
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
' The example displays the following output:
'    Created original string...
'    
'    Decoded string using UnicodeEncoding.GetString()...
'    original = decoded: False
'    Code points in original string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    Code points in decoded string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    
'    Decoded string using UnicodeEncoding.Decoder.GetString()...
'    original = decoded: True
```

## <a name="choosing-a-fallback-strategy"></a>Выбор резервной стратегии

Когда метод пытается закодировать или декодировать символ, но не находит сопоставления, он должен использовать резервную стратегию, определяющую, как должно обрабатываться отсутствие сопоставления. Существует три типа резервных стратегий: 

* стратегия наилучшего соответствия;

* стратегия замены;

* стратегия исключения.

> [!IMPORTANT]
> При операциях кодирования наиболее часто проблемы возникают, когда символ Юникода не удается сопоставить с определенной кодировкой кодовой страницы. При операциях декодирования наиболее часто проблемы возникают, когда недопустимую последовательность байтов не удается преобразовать в допустимые символы Юникода. Поэтому необходимо знать, какую резервную стратегию использует определенный объект кодировки. По возможности при создании экземпляра объекта следует указывать резервную стратегию, используемую объектом кодировки.
 
### <a name="best-fit-fallback"></a>стратегия наилучшего соответствия;

Если символ не имеет точного соответствия в целевой кодировке, кодировщик может попытаться сопоставить его с похожим символом. (Стратегия наилучшего соответствия связана с проблемами, возникающими скорее при кодировании, чем при декодировании. Существует лишь небольшое число кодовых страниц, символы которых нельзя сопоставить с Юникодом.) Стратегия наилучшего соответствия является стратегией по умолчанию для кодовых страниц и двухбайтовых кодировок, извлекаемых перегрузками [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) и [Encoding.GetEncoding(String)](xref:System.Text.Encoding.GetEncoding(System.String)).

> [!NOTE]
> Теоретически классы кодировок Юникода, доступные в .NET ([UTF8Encoding](xref:System.Text.UTF8Encoding), [UnicodeEncoding](xref:System.Text.UnicodeEncoding) и [UTF32Encoding](xref:System.Text.UTF32Encoding)), поддерживают все символы всех наборов символов, поэтому их можно использовать, чтобы избежать проблем со стратегией наилучшего соответствия. 
 

Стратегии наилучшего соответствия для разных кодовых страниц различаются. Не все стратегии подробно задокументированы. Например, для некоторых кодовых страниц полноширинные латинские символы сопоставляются с более распространенными полуширинными символами. Для других кодовых страниц такое сопоставление не выполняется. Даже в случае применения активной стратегии наилучшего соответствия для некоторых символов некоторых кодировок отсутствует возможное сопоставление. Например, для идеографических символов китайского алфавита отсутствуют корректные сопоставления с символами кодовой страницы 1252. В этом случае используются замещающие строки. По умолчанию в качестве замещающей строки используется знак вопроса (U+003F).

В примере ниже используется кодовая страница 1252 (кодовая страница Windows для западноевропейских языков) для иллюстрации стратегии наилучшего соответствия и ее недостатков. Метод [Encoding.GetEncoding(Int32](xref:System.Text.Encoding.GetEncoding(System.Int32)) используется для получения объекта кодировки для кодовой страницы 1252. По умолчанию для неподдерживаемых символов Юникода используется стратегия наилучшего соответствия. В примере создается экземпляр строки, содержащий три символа, не относящихся к ASCII (прописная латинская буква S в кружке (U+24C8), надстрочный индекс 5 (U+2075) и знак бесконечности (U+221E)), разделенные пробелами. Как видно из выходных данных примера, при кодировке строки три исходных отличных от пробела символа заменяются вопросительным знаком (U+003F), цифрой пять (U+0035) и цифрой восемь (U+0038). Цифра восемь — особенно неудачная замена неподдерживаемого знака бесконечности, а вопросительный знак показывает, что для исходного символа сопоставление не найдено.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Get an encoding for code page 1252 (Western Europe character set).
      Encoding cp1252 = Encoding.GetEncoding(1252);

      // Define and display a string.
      string str = "\u24c8 \u2075 \u221e";
      Console.WriteLine("Original string: " + str);
      Console.Write("Code points in string: ");
      foreach (var ch in str)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");   

      // Encode a Unicode string.
      Byte[] bytes = cp1252.GetBytes(str);
      Console.Write("Encoded bytes: ");
      foreach (byte byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the string.
      string str2 = cp1252.GetString(bytes);
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2));
      if (! str.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
      }
   }
}
// The example displays the following output:
//       Original string: Ⓢ ⁵ ∞
//       Code points in string: 24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 35 20 38
//       
//       String round-tripped: False
//       ? 5 8
//       003F 0020 0035 0020 0038
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      ' Get an encoding for code page 1252 (Western Europe character set).
      Dim cp1252 As Encoding = Encoding.GetEncoding(1252)

      ' Define and display a string.
      Dim str As String = String.Format("{0} {1} {2}", ChrW(&h24c8), ChrW(&H2075), ChrW(&h221E))
      Console.WriteLine("Original string: " + str)
      Console.Write("Code points in string: ")
      For Each ch In str
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next
      Console.WriteLine()   
      Console.WriteLine()

      ' Encode a Unicode string.
      Dim bytes() As Byte = cp1252.GetBytes(str)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the string.
      Dim str2 As String = cp1252.GetString(bytes)
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2))
      If Not str.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Original string: Ⓢ ⁵ ∞
'       Code points in string: 24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 35 20 38
'       
'       String round-tripped: False
'       ? 5 8
'       003F 0020 0035 0020 0038
```

По умолчанию для объекта [Encoding](xref:System.Text.Encoding) применяется стратегия наилучшего соответствия, при которой данные в формате Юникод кодируются в формат кодовой страницы. Ряд приложений предыдущих версий построен с учетом этой стратегии. Однако в целях безопасности в большинстве новых приложений не рекомендуется применять эту стратегию. Например, приложениям не следует выполнять кодировку доменного имени в режиме наилучшего соответствия.

> [!Note]
> Вы также можете реализовать пользовательскую стратегию наилучшего соответствия для кодировки. Подробнее см. в разделе [Реализация пользовательской резервной стратегии](#implementing-a-custom-fallback-strategy).
 
Если стратегия наилучшего соответствия задана по умолчанию для объекта кодировки, вы можете выбрать другую резервную стратегию при извлечении объекта [Encoding](xref:System.Text.Encoding) путем вызова перегрузки [Encoding.GetEncoding(Int32, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)) или [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)). В следующем разделе приводится пример, где каждый символ, который не удается сопоставить с кодовой страницей 1252, заменяется звездочкой (\*).

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

### <a name="replacement-fallback"></a>стратегия замены;

Когда символ не имеет точного соответствия в целевой схеме и нет подходящего символа, с которым его можно сопоставить, приложение может использовать замещающий символ или строку. Так по умолчанию поступает декодер Юникода, заменяющий любую двухбайтовую последовательность, которую он не может декодировать, замещающим символом (U+FFFD). Кроме того, это поведение по умолчанию класса [ASCIIEncoding](xref:System.Text.ASCIIEncoding), заменяющего каждый символ, который не удается кодировать или декодировать, вопросительным знаком. В примере ниже показана замена символов для строки Юникода из предыдущего примера. Как видно из выходных данных, каждый символ, который не удается декодировать в байтовое значение ASCII, заменяется 0x3F, то есть кодом ASCII для вопросительного знака.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.ASCII;

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 3F 20 3F
//       
//       Round-trip: False
//       ? ? ?
//       003F 0020 003F 0020 003F
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.Ascii

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 3F 20 3F
'       
'       Round-trip: False
'       ? ? ?
'       003F 0020 003F 0020 003F
```

В .NET есть классы [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) и [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback), подставляющие замещающую строку, если не удается точно сопоставить символ при кодировании или декодировании. По умолчанию эта замещающая строка — вопросительный знак, но вы можете вызвать перегрузку конструктора класса, чтобы выбрать другую строку. Как правило, замещающая строка — это отдельный символ, хотя это необязательно. В примере ниже поведение кодировщика кодовой страницы 1252 изменяется путем создания экземпляра объекта [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback), который использует символ звездочки (\*) в качестве замещающей строки.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

> [!NOTE]
> Также можно реализовать класс замены для кодировки. Подробнее см. в разделе [Реализация пользовательской резервной стратегии](#implementing-a-custom-fallback-strategy).
 
Помимо вопросительного знака (U+003F) в качестве замещающей строки часто используется замещающий символ Юникода (U+FFFD), особенно при декодировании последовательностей байтов, которые не удается преобразовать в символы Юникода. Однако вы можете выбрать любую замещающую строку, в том числе из нескольких символов.

### <a name="exception-fallback"></a>стратегия исключения.

Вместо подстановки наиболее подходящей или замещающей строки кодировщик может создавать исключение [EncoderFallbackException](xref:System.Text.EncoderFallbackException), если не удается закодировать набор символов, а декодер — создавать исключение [DecoderFallbackException](xref:System.Text.DecoderFallbackException), если не удается декодировать массив байтов. Для создания исключения в операциях кодирования и декодирования методу [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) необходимо предоставить объект [EncoderFallbackException](xref:System.Text.EncoderFallbackException) или [DecoderFallbackException](xref:System.Text.DecoderFallbackException), соответственно. В примере ниже иллюстрируется резервная стратегия исключения с классом ASCIIEncoding.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", 
                                          new EncoderExceptionFallback(), 
                                          new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = {};
      try {
         bytes = enc.GetBytes(str1);
         Console.Write("Encoded bytes: ");
         foreach (var byt in bytes)
            Console.Write("{0:X2} ", byt);

         Console.WriteLine();
      }
      catch (EncoderFallbackException e) {
         Console.Write("Exception: ");
         if (e.IsUnknownSurrogate())
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index);
         else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index);
         return;
      }
      Console.WriteLine();

      // Decode the ASCII bytes.
      try {
         string str2 = enc.GetString(bytes);
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
         if (! str1.Equals(str2)) {
            Console.WriteLine(str2);
            foreach (var ch in str2)
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

            Console.WriteLine();
         } 
      }
      catch (DecoderFallbackException e) {
         Console.Write("Unable to decode byte(s) ");
         foreach (byte unknown in e.BytesUnknown)
            Console.Write("0x{0:X2} ");

         Console.WriteLine("at index {0}", e.Index);
      }
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Exception: Unable to encode 0x24C8 at index 0.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", 
                                                 New EncoderExceptionFallback(), 
                                                 New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = {}
      Try
         bytes = enc.GetBytes(str1)
         Console.Write("Encoded bytes: ")
         For Each byt In bytes
            Console.Write("{0:X2} ", byt)
         Next
         Console.WriteLine()
      Catch e As EncoderFallbackException
         Console.Write("Exception: ")
         If e.IsUnknownSurrogate() Then
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index)
         Else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index)
         End If                              
         Exit Sub
      End Try
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Try
         Dim str2 As String = enc.GetString(bytes)
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
         If Not str1.Equals(str2) Then
            Console.WriteLine(str2)
            For Each ch In str2
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
            Next    
            Console.WriteLine()
         End If 
      Catch e As DecoderFallbackException
         Console.Write("Unable to decode byte(s) ")
         For Each unknown As Byte In e.BytesUnknown
            Console.Write("0x{0:X2} ")
         Next
         Console.WriteLine("at index {0}", e.Index)
      End Try
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Exception: Unable to encode 0x24C8 at index 0.
```

> [!NOTE]
> Вы также можете реализовать пользовательский обработчик исключений для операции кодирования. Подробнее см. в разделе [Реализация пользовательской резервной стратегии](#implementing-a-custom-fallback-strategy).
 
Объекты [EncoderFallbackException](xref:System.Text.EncoderFallbackException) и [DecoderFallbackException](xref:System.Text.DecoderFallbackException) предоставляют следующую информацию о состоянии, вызвавшем исключение. 

* Объект [EncoderFallbackException](xref:System.Text.EncoderFallbackException) включает метод [IsUnknownSurrogate](xref:System.Text.EncoderFallbackException.IsUnknownSurrogate), указывающий, представляют ли символы (или символ), которые не удается закодировать, неизвестную замещающую пару (тогда метод возвращает значение `true`) или неизвестный отдельный символ (тогда метод возвращает значение `false`). Символы замещающей пары доступны в свойствах [EncoderFallbackException.CharUnknownHigh](xref:System.Text.EncoderFallbackException.CharUnknownHigh) и [EncoderFallbackException.CharUnknownLow](xref:System.Text.EncoderFallbackException.CharUnknownLow). Неизвестный отдельный символ доступен в свойстве [EncoderFallbackException.CharUnknown](xref:System.Text.EncoderFallbackException.CharUnknown). Свойство [EncoderFallbackException.Index](xref:System.Text.EncoderFallbackException.Index) указывает позицию первого символа, который не удалось закодировать, в строке.

* Объект [DecoderFallbackException](xref:System.Text.DecoderFallbackException) включает свойство [BytesUnknown](xref:System.Text.DecoderFallbackException.BytesUnknown), возвращающее массив байтов, которые не удается декодировать. Свойство [DecoderFallbackException.Index](xref:System.Text.DecoderFallbackException.Index) указывает начальную позицию неизвестных байтов.

Несмотря на то, что объекты [EncoderFallbackException](xref:System.Text.EncoderFallbackException) и [DecoderFallbackException](xref:System.Text.DecoderFallbackException) предоставляют достаточно подробную диагностическую информацию об исключении, они не предоставляют доступ к буферу кодирования или декодирования. Поэтому они не позволяют заменять или исправлять недопустимые данные в методе кодирования или декодирования.

## <a name="implementing-a-custom-fallback-strategy"></a>Реализация пользовательской резервной стратегии

Помимо встроенной стратегии наилучшего соответствия, реализованной кодовыми страницами, платформа .NET содержит следующие классы для реализации резервной стратегии:

* классы [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) и [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) можно использовать для замены символов в операциях кодирования;

* классы [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) и [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) можно использовать для замены символов в операциях декодирования;

* классы [EncoderExceptionFallback](xref:System.Text.EncoderExceptionFallback) и [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) можно использовать для создания исключения [EncoderFallbackException](xref:System.Text.EncoderFallbackException), когда символ не удается закодировать;

* классы [DecoderExceptionFallback](xref:System.Text.DecoderExceptionFallback) и [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) можно использовать для создания исключения [DecoderFallbackException](xref:System.Text.DecoderFallbackException), когда символ не удается декодировать.

Кроме того, можно реализовать пользовательское решение, использующее резервную стратегию наилучшего соответствия или стратегию исключения, выполнив указанные ниже действия. 

1. Создайте класс, производный от [EncoderFallback](xref:System.Text.EncoderFallback), для операций кодирования и класс, производный от [DecoderFallback](xref:System.Text.DecoderFallback), для операций декодирования.

2. Создайте класс, производный от [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer), для операций кодирования и класс, производный от [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer), для операций декодирования.

3. Для задания резервной стратегии исключения, если классы [EncoderFallbackException](xref:System.Text.EncoderFallbackException) и [DecoderFallbackException](xref:System.Text.DecoderFallbackException) не отвечают вашим требованиям, следует наследовать класс от объекта исключения, например [Exception](xref:System.Exception) или [ArgumentException](xref:System.ArgumentException).

### <a name="deriving-from-encoderfallback-or-decoderfallback"></a>Наследование от класса EncoderFallback или класса DecoderFallback

Для реализации пользовательской резервной стратегии необходимо создать класс, наследующий от [EncoderFallback](xref:System.Text.EncoderFallback) для операций кодирования и от класса [DecoderFallback](xref:System.Text.DecoderFallback) для операций декодирования. Экземпляры этих классов передаются в метод [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) и служат посредниками между классом кодировки и реализацией резервной стратегии.

При создании пользовательской резервной стратегии для кодировщика или декодера необходимо реализовать следующие члены:

* Свойство [EncoderFallback.MaxCharCount](xref:System.Text.EncoderFallback.MaxCharCount) или [DecoderFallback.MaxCharCount](xref:System.Text.DecoderFallback.MaxCharCount), возвращающее максимально возможное число символов, которое может использоваться для замены одного символа в стратегиях наилучшего соответствия, замены или исключения. Для пользовательской резервной стратегии исключения его значение равно нулю. 

* Метод [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) или [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer), возвращающий пользовательскую реализацию [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) или [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer). Метод вызывается кодировщиком, когда он встречает первый символ, который не удается закодировать, или декодером, когда он встречает первый байт, который не удается декодировать.

### <a name="deriving-from-encoderfallbackbuffer-or-decoderfallbackbuffer"></a>Наследование от класса EncoderFallbackBuffer или класса DecoderFallbackBuffer

Для реализации пользовательской резервной стратегии необходимо также создать класс, наследующий от [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) для операций кодирования и от класса [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) для операций декодирования. Экземпляры этих классов возвращаются методом `CreateFallbackBuffer` классов [EncoderFallback](xref:System.Text.EncoderFallback) и [DecoderFallback](xref:System.Text.DecoderFallback). Метод [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) вызывается кодировщиком, когда он встречает первый символ, который не удается закодировать, а метод [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer) вызывается декодером, когда он встречает один или несколько байтов, которые не удается декодировать. Классы [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) и [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) предоставляют реализацию резервной стратегии. Каждый экземпляр представляет буфер, содержащий символы резервной стратегии, которые заменят символ, который не удалось закодировать, или последовательность байтов, которую не удалось декодировать.

При создании пользовательской резервной стратегии для кодировщика или декодера необходимо реализовать следующие члены:

* Метод [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.%23ctor) или [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)). Метод [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.Fallback(System.Char,System.Char,System.Int32)) вызывается кодировщиком, чтобы предоставить резервный буфер со сведениями о символе, который не удается кодировать. Так как символ, который требуется закодировать, может быть замещающей парой, этот метод перегружается. Одной перегрузке передается символ, который нужно закодировать, и его индекс в строке. Второй перегрузке передаются верхний и нижний замещающий знаки и их индекс в строке. Метод [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)) вызывается декодером, чтобы предоставить резервный буфер со сведениями о байтах, которые не удается декодировать. Этому методу передается массив байтов, которые не удалось декодировать, а также индекс первого байта. Метод резервной стратегии должен возвращать значение `true`, если резервный буфер может предоставить наилучшим образом соответствующий или замещающий символ (или символы); в противном случае он должен возвращать значение `false`. При использовании стратегии исключения метод резервной стратегии должен создавать исключение.

* Метод [EncoderFallbackBuffer.GetNextChar](xref:System.Text.EncoderFallbackBuffer.GetNextChar) или [DecoderFallbackBuffer.GetNextChar](xref:System.Text.DecoderFallbackBuffer.GetNextChar), который вызывается кодировщиком или декодером многократно для получения следующего символа из резервного буфера. После возврата всех резервных символов метод должен вернуть символ U+0000. 

* Свойство [EncoderFallbackBuffer.Remaining](xref:System.Text.EncoderFallbackBuffer.Remaining) или [DecoderFallbackBuffer.Remaining](xref:System.Text.DecoderFallbackBuffer.Remaining), которое возвращает количество символов, оставшихся в резервном буфере.

* Метод [EncoderFallbackBuffer.MovePrevious](xref:System.Text.EncoderFallbackBuffer.MovePrevious) или [DecoderFallbackBuffer.MovePrevious](xref:System.Text.DecoderFallbackBuffer.MovePrevious), который перемещает текущую позицию в резервном буфере к предыдущему символу.

* Метод [EncoderFallbackBuffer.Reset](xref:System.Text.EncoderFallbackBuffer.Reset) или [DecoderFallbackBuffer.Reset](xref:System.Text.DecoderFallbackBuffer.Reset), повторно инициализирующий резервный буфер.

Если реализована резервная стратегия наилучшего соответствия или замены, классы, унаследованные от [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) и [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer), также имеют два закрытых поля экземпляра: точное число символов в буфере и индекс в буфере следующего символа, который нужно вернуть.

### <a name="an-encoderfallback-example"></a>Пример EncoderFallback

В примере выше использовалась стратегия замены символов Юникода, не соответствующих символам ASCII, звездочкой (\*). В примере ниже используется пользовательская резервная стратегия наилучшего соответствия для получения более удачного сопоставления символов, отсутствующих в ASCII.

В приведенном коде определяется класс с именем `CustomMapper`, производный от [EncoderFallback](xref:System.Text.EncoderFallback), для обработки наилучшего сопоставления символов, отсутствующих в ASCII. Его метод `CreateFallbackBuffer` возвращает объект `CustomMapperFallbackBuffer`, предоставляющий реализацию [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer). Класс `CustomMapper` использует объект [Dictionary&lt;TKey, TValue&gt;](xref:System.Collections.Generic.Dictionary%602) для хранения сопоставлений неподдерживаемых символов Юникода (значение ключа) и соответствующих им 8-битных символов (которые хранятся в двух последовательных байтах в виде 64-разрядного целого числа). Чтобы это сопоставление было доступно резервному буферу, экземпляр `CustomMapper` передается в качестве параметра конструктору класса `CustomMapperFallbackBuffer`. Так как самое длинное сопоставление — это строка INF для символа Юникода с кодом U+221E, свойство `MaxCharCount` возвращает значение 3. 

```csharp
public class CustomMapper : EncoderFallback
{
   public string DefaultString;
   internal Dictionary<ushort, ulong> mapping;

   public CustomMapper() : this("*")
   {   
   }

   public CustomMapper(string defaultString)
   {
      this.DefaultString = defaultString;

      // Create table of mappings
      mapping = new Dictionary<ushort, ulong>();
      mapping.Add(0x24C8, 0x53);
      mapping.Add(0x2075, 0x35);
      mapping.Add(0x221E, 0x49004E0046);
   }

   public override EncoderFallbackBuffer CreateFallbackBuffer()
   {
      return new CustomMapperFallbackBuffer(this);
   }

   public override int MaxCharCount
   {
      get { return 3; }
   } 
}
```

```vb
Public Class CustomMapper : Inherits EncoderFallback
   Public DefaultString As String
   Friend mapping As Dictionary(Of UShort, ULong)

   Public Sub New()
      Me.New("?")
   End Sub

   Public Sub New(ByVal defaultString As String)
      Me.DefaultString = defaultString

      ' Create table of mappings
      mapping = New Dictionary(Of UShort, ULong)
      mapping.Add(&H24C8, &H53)
      mapping.Add(&H2075, &H35)
      mapping.Add(&H221E, &H49004E0046)
   End Sub

   Public Overrides Function CreateFallbackBuffer() As System.Text.EncoderFallbackBuffer
      Return New CustomMapperFallbackBuffer(Me)
   End Function

   Public Overrides ReadOnly Property MaxCharCount As Integer
      Get
         Return 3
      End Get
   End Property
End Class
```

В примере кода ниже определяется класс `CustomMapperFallbackBuffer`, производный от [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer). Словарь, содержащий сопоставления наилучшего соответствия и определенный в экземпляре класса `CustomMapper`, доступен из конструктора класса. Его метод `Fallback` возвращает значение `true`, если какие-либо символы Юникода, которые не удается кодировать кодировщику ASCII, определены в словаре сопоставлений; в противном случае возвращается значение `false`. Для каждого резервного действия закрытая переменная `count` указывает число символов, которые осталось вернуть, а закрытая переменная `index` указывает позицию в буфере строк (значение `charsToReturn`) следующего символа, который нужно вернуть. 

```csharp
public class CustomMapperFallbackBuffer : EncoderFallbackBuffer
{
   int count = -1;                   // Number of characters to return
   int index = -1;                   // Index of character to return
   CustomMapper fb; 
   string charsToReturn; 

   public CustomMapperFallbackBuffer(CustomMapper fallback)
   {
      this.fb = fallback;
   }

   public override bool Fallback(char charUnknownHigh, char charUnknownLow, int index)
   {
      // Do not try to map surrogates to ASCII.
      return false;
   }

   public override bool Fallback(char charUnknown, int index)
   {
      // Return false if there are already characters to map.
      if (count >= 1) return false;

      // Determine number of characters to return.
      charsToReturn = String.Empty;

      ushort key = Convert.ToUInt16(charUnknown);
      if (fb.mapping.ContainsKey(key)) {
         byte[] bytes = BitConverter.GetBytes(fb.mapping[key]);
         int ctr = 0;
         foreach (var byt in bytes) {
            if (byt > 0) {
               ctr++;
               charsToReturn += (char) byt;
            }
         }
         count = ctr;
      }
      else {
         // Return default.
         charsToReturn = fb.DefaultString;
         count = 1;
      }
      this.index = charsToReturn.Length - 1;

      return true;
   }

   public override char GetNextChar()
   {
      // We'll return a character if possible, so subtract from the count of chars to return.
      count--;
      // If count is less than zero, we've returned all characters.
      if (count < 0) 
         return '\u0000';

      this.index--;
      return charsToReturn[this.index + 1];
   }

   public override bool MovePrevious()
   {
      // Original: if count >= -1 and pos >= 0
      if (count >= -1) {
         count++;
         return true;
      }
      else {
         return false;
      }
   }

   public override int Remaining 
   {
      get { return count < 0 ? 0 : count; }
   }

   public override void Reset()
   {
      count = -1;
      index = -1;
   }
}
```

```vb
Public Class CustomMapperFallbackBuffer : Inherits EncoderFallbackBuffer

   Dim count As Integer = -1        ' Number of characters to return
   Dim index As Integer = -1        ' Index of character to return
   Dim fb As CustomMapper
   Dim charsToReturn As String

   Public Sub New(ByVal fallback As CustomMapper)
      MyBase.New()
      Me.fb = fallback
   End Sub

   Public Overloads Overrides Function Fallback(ByVal charUnknownHigh As Char, ByVal charUnknownLow As Char, ByVal index As Integer) As Boolean
      ' Do not try to map surrogates to ASCII.
      Return False
   End Function

   Public Overloads Overrides Function Fallback(ByVal charUnknown As Char, ByVal index As Integer) As Boolean
      ' Return false if there are already characters to map.
      If count >= 1 Then Return False

      ' Determine number of characters to return.
      charsToReturn = String.Empty

      Dim key As UShort = Convert.ToUInt16(charUnknown)
      If fb.mapping.ContainsKey(key) Then
         Dim bytes() As Byte = BitConverter.GetBytes(fb.mapping.Item(key))
         Dim ctr As Integer
         For Each byt In bytes
            If byt > 0 Then
               ctr += 1
               charsToReturn += Chr(byt)
            End If
         Next
         count = ctr
      Else
         ' Return default.
         charsToReturn = fb.DefaultString
         count = 1
      End If
      Me.index = charsToReturn.Length - 1

      Return True
   End Function

   Public Overrides Function GetNextChar() As Char
      ' We'll return a character if possible, so subtract from the count of chars to return.
      count -= 1
      ' If count is less than zero, we've returned all characters.
      If count < 0 Then Return ChrW(0)

      Me.index -= 1
      Return charsToReturn(Me.index + 1)
   End Function

   Public Overrides Function MovePrevious() As Boolean
      ' Original: if count >= -1 and pos >= 0
      If count >= -1 Then
         count += 1
         Return True
      Else
         Return False
      End If
   End Function

   Public Overrides ReadOnly Property Remaining As Integer
      Get
         Return If(count < 0, 0, count)
      End Get
   End Property

   Public Overrides Sub Reset()
      count = -1
      index = -1
   End Sub
End Class
```

В приведенном ниже коде создается экземпляр объекта `CustomMapper`, который передается в метод [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)). Выходные данные показывают, что реализация стратегии наилучшего соответствия успешно обрабатывает три символа исходной строки, отсутствующие в ASCII.

```csharp
using System;
using System.Collections.Generic;
using System.Text;

class Program
{
   static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", new CustomMapper(), new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      for (int ctr = 0; ctr <= str1.Length - 1; ctr++) {
         Console.Write("{0} ", Convert.ToUInt16(str1[ctr]).ToString("X4"));
         if (ctr == str1.Length - 1) 
            Console.WriteLine();
      }
      Console.WriteLine();

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);

      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      }
   }
}
```

```vb
Imports System.Text
Imports System.Collections.Generic

Module Module1

   Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", New CustomMapper(), New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&H24C8), ChrW(&H2075), ChrW(&H221E))
      Console.WriteLine(str1)
      For ctr As Integer = 0 To str1.Length - 1
         Console.Write("{0} ", Convert.ToUInt16(str1(ctr)).ToString("X4"))
         If ctr = str1.Length - 1 Then Console.WriteLine()
      Next
      Console.WriteLine()

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
```

## <a name="see-also"></a>См. также

[System.Text.Encoder](xref:System.Text.Encoder)

[System.Text.EncoderFallback](xref:System.Text.EncoderFallback)

[System.Text.Decoder](xref:System.Text.Decoder)

[System.Text.DecoderFallback](xref:System.Text.DecoderFallback)

[System.Text.Encoding](xref:System.Text.Encoding)







<!--HONumber=Nov16_HO3-->


