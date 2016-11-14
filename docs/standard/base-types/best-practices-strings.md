---
title: "Рекомендации по использованию строк"
description: "Рекомендации по использованию строк"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b3cefaa4-0a3f-4a96-aba9-1de30fb07c29
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 3efd30bade564fe1b7dbf93237a9ff40c58c5f1e

---

# <a name="best-practices-for-using-strings"></a>Рекомендации по использованию строк

Платформа .NET предоставляет расширенную поддержку разработки локализованных и глобализованных приложений и упрощает применение правил текущего или какого-то определенного языка и региональных параметров при выполнении общих операций, таких как сортировка строк и их отображение. Однако сортировка и сравнение строк не всегда выполняется с учетом языка и региональных параметров. Например, строки, которые используются внутри приложения, как правило, должны обрабатываться одинаково независимо от выбранного языка и региональных параметров. Если независимые от языка и региональных параметров строковые данные, такие как теги XML, теги HTML, имена пользователей, пути к файлам и имена системных объектов, интерпретируются как зависимые от языка и региональных параметров, в коде приложения могут возникать незначительные ошибки, может наблюдаться низкая производительность, а в некоторых случаях и проблемы безопасности.

В этом разделе рассматриваются методы сортировки, сравнения строк и использования прописных и строчных букв в .NET, представлены рекомендации по выбору подходящего метода обработки строк и дополнительная информация об этих методах. Кроме того, рассматривается отображение и хранение форматированных данных, например числовых данных или даты и времени. 

В этом разделе содержатся следующие подразделы:

* [Рекомендации по использованию строк](#recommendations-for-string-usage)

* [Явное задание сравнений строк](#specifying-string-comparisons-explicitly)

* [Подробные сведения о сравнении строк](#the-details-of-string-comparison)

* [Выбор элемента StringComparison для вызова своего метода](#choosing-a-stringcomparison-member-for-your-method-call)

* [Общие методы сравнения строк](#common-string-comparison-methods)

* [Методы, сравнивающие строки опосредованно](#methods-that-perform-string-comparison-indirectly)

* [Отображение и сохранение форматированных данных](#displaying-and-persisting-formatted-data)

## <a name="recommendations-for-string-usage"></a>Рекомендации по использованию строк

Если вы выполняете разработку на платформе .NET, следуйте нескольким простым рекомендациям по работе со строками. 

* Используйте перегрузки, которые явно задают правила сравнения строк для операций со строками. Как правило, это подразумевает вызов перегрузки метода, который имеет параметр типа [StringComparison](xref:System.StringComparison).

* Используйте [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) для сравнений в качестве безопасной альтернативы по умолчанию для сопоставления строк независимо от языка и региональных параметров.

* Используйте сравнения с [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) для повышения производительности.

* Используйте строковые операции, основанные на [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture), при отображении выходных данных для пользователя.

* Используйте нелингвистические значения [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) вместо строковых операций на основе [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture), если лингвистические аспекты в сравнении не важны (например, выполняется сравнение символов).

* Используйте метод [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) вместо [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) при нормализации строк для сравнения.

* Используйте перегрузку метода [String](xref:System.String) `Equals` для проверки равенства двух строк.

* Используйте перегрузку методов [String](xref:System.String) `Compare` и [String.CompareTo](xref:System.String.CompareTo(System.String)) для сортировки строк, а не для проверки их равенства.

* Используйте форматирование с учетом языка и региональных параметров для отображения нестроковых данных, например чисел и дат, в пользовательском интерфейсе. Для сохранения нестроковых данных в строковой форме используйте форматирование инвариантного языка и региональных параметров.

При использовании строк избегайте следующих действий.

* Не используйте перегрузки, которые не задают правила сравнения строк для операций со строками в явной или неявной форме. 

* Не используйте перегрузку метода [String](xref:System.String) `Compare` или [String.CompareTo](xref:System.String.CompareTo(System.String)) и проверяйте возвращаемое значение (ноль), чтобы определить, равны ли строки.

* Не используйте форматирование с учетом языка и региональных параметров для сохранения числовых данных или данных даты и времени в виде строки.

## <a name="specifying-string-comparisons-explicitly"></a>Явное задание сравнений строк

Большинство методов обработки строк в .NET являются перегруженными. Как правило, одна или несколько перегрузок принимают настройки по умолчанию, а другие — нет и вместо этого определяют требуемый точный способ сравнения и обработки строк. Большинство методов, не использующих значения по умолчанию, включают параметр типа [StringComparison](xref:System.StringComparison), который представляет собой перечисление, явно задающее правила сравнения строк по языку, региональным параметрам и регистру. В следующей таблице описаны элементы перечисления [StringComparison](xref:System.StringComparison). 

Элемент StringComparison | Описание
----------------------- | -----------
[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) | Выполняет сравнение с учетом регистра, используя текущий язык и региональные параметры.
[CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) | Выполняет сравнение без учета регистра, используя текущий язык и региональные параметры.
[StringComparison.Ordinal](xref:System.StringComparison.Ordinal) | Выполняет порядковое сравнение.
[StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) | Выполняет порядковое сравнение без учета регистра.

Например, метод [String](xref:System.String) `IndexOf`, который возвращает индекс подстроки в объект [String](xref:System.String), соответствующий символу или строке, имеет девять перегрузок:

* [IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)) и [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)), которые по умолчанию выполняют порядковый поиск символа в строке (с учетом регистра и без учета языка и региональных параметров).

* [IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)) и [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)), которые по умолчанию выполняют порядковый поиск символа в строке (с учетом регистра и без учета языка и региональных параметров).

* [IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)) и [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)), которые включают параметр типа StringComparison, что позволяет задать форму сравнения.

Рекомендуется выбрать перегрузку, не использующую значения по умолчанию, по следующим причинам.

* Некоторые перегрузки с параметрами по умолчанию (те, которые выполняют поиск [Char](xref:System.Char) в экземпляре строки) выполняют порядковое сравнение, в то время как другие (выполняющие поиск строки в экземпляре строки) учитывают язык и региональные параметры. Сложно запомнить, какое значение по умолчанию использует тот или иной метод, перегрузки легко перепутать.

* Назначение кода, вызовы методов в котором зависят от значений по умолчанию, не ясно. В следующем примере, где используются значения по умолчанию, сложно определить, действительно ли разработчик намеревался выполнить порядковое или лингвистическое сравнение двух строк или различие регистра между `protocol` и http могло привести к тому, что проверка на равенство возвратит значение `false`.

  ```csharp
  string protocol = GetProtocol(url);       
  if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
     // ...Code to handle HTTP protocol.
  }
  else {
     throw new InvalidOperationException();
  }
  ```

  ```vb
  Dim protocol As String = GetProtocol(url)       
  If String.Equals(protocol, "http") Then
    ' ...Code to handle HTTP protocol.
  Else
     Throw New InvalidOperationException()
  End If
  ```

В общем случае рекомендуется вызывать метод, который не зависит от значений по умолчанию, поскольку это делает назначение кода однозначным. Это, в свою очередь, делает код более читаемым и упрощает отладку и обслуживание. В следующем примере рассматриваются вопросы, возникшие в предыдущем примере. Он явно демонстрирует, что используется порядковое сравнение и что различия регистра игнорируются. 

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase) Then
   ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

## <a name="the-details-of-string-comparison"></a>Подробные сведения о сравнении строк

Сравнение строк является основой многих связанных со строками операций, в частности сортировки и проверки на равенство. Строки сортируются в определенном порядке: если my отображается до string в сортированном списке строк, текст my должен быть меньше или равен тексту string. Кроме того, неявное сравнение определяет равенство. Операция сравнения возвращает 0 для строк, которые она считает равными. Правильно интерпретировать это следующим образом: ни одна из строк не меньше другой. Наиболее значимые операции со строками включают обе следующие процедуры или хотя бы одну из них: сравнение с другой строкой и выполнение правильно определенной операции сортировки.

Однако оценка двух строк на равенство или порядок сортировки не дает единственно верного результата; результат также зависит от критериев, используемых для сравнения строк. В частности, операции сравнения строк, которые являются порядковыми или основаны на правилах учета регистра или сортировки текущего языка и региональных параметров или инвариантного языка и региональных параметров (независимые от языкового стандарта региональные параметры на основе английского языка), могут давать разные результаты.

### <a name="string-comparisons-that-use-the-current-culture"></a>Сравнение строк с использованием текущего языка и региональных параметров

Одним из критериев является использование правил текущего языка и региональных параметров при сравнении строк. В сравнениях, основанных на текущем языке и региональных параметрах, используется текущий язык, региональные параметры или языковой стандарт потока. Следует всегда использовать сравнения на основе текущего языка и региональных параметров, если речь идет о лингвистически релевантных данных и данных, отражающих взаимодействие с пользователем, где важны язык и региональные параметры. 

Однако поведение сравнения и использования регистра в .NET меняется при изменении языка и региональных параметров. Это происходит, если приложение выполняется на компьютере с другим языком и региональными параметрами, нежели на компьютере, где приложение было разработано, либо если выполняющий поток меняет свой язык и региональные параметры. Это поведение является преднамеренным, однако до сих пор остается неочевидным для многих разработчиков. В следующем примере показаны различия в порядке сортировки в американском английском (en-US) и шведском языке (sv-SE). Обратите внимание, что слова ångström, Windows и Visual Studio показаны в разных местах массива сортированных строк.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] values= { "able", "ångström", "apple", "Æble", 
                         "Windows", "Visual Studio" };
      Array.Sort(values);
      DisplayArray(values);

      // Change culture to Swedish (Sweden).
      string originalCulture = CultureInfo.CurrentCulture.Name;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("sv-SE");
      Array.Sort(values);
      DisplayArray(values);

      // Restore the original culture.
      Thread.CurrentThread.CurrentCulture = new CultureInfo(originalCulture);
    }

    private static void DisplayArray(string[] values)
    {
      Console.WriteLine("Sorting using the {0} culture:",  
                        CultureInfo.CurrentCulture.Name);
      foreach (string value in values)
         Console.WriteLine("   {0}", value);

      Console.WriteLine();
    }
}
// The example displays the following output:
//       Sorting using the en-US culture:
//          able
//          Æble
//          ångström
//          apple
//          Visual Studio
//          Windows
//       
//       Sorting using the sv-SE culture:
//          able
//          Æble
//          apple
//          Windows
//          Visual Studio
//          ångström
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim values() As String = { "able", "ångström", "apple", _
                                 "Æble", "Windows", "Visual Studio" }
      Array.Sort(values)
      DisplayArray(values)

      ' Change culture to Swedish (Sweden).
      Dim originalCulture As String = CultureInfo.CurrentCulture.Name
      Thread.CurrentThread.CurrentCulture = New CultureInfo("sv-SE")
      Array.Sort(values)
      DisplayArray(values)

      ' Restore the original culture.
      Thread.CurrentThread.CurrentCulture = New CultureInfo(originalCulture)
    End Sub

    Private Sub DisplayArray(values() As String)
      Console.WRiteLine("Sorting using the {0} culture:", _ 
                        CultureInfo.CurrentCulture.Name)
      For Each value As String In values
         Console.WriteLine("   {0}", value)
      Next
      Console.WriteLine()   
    End Sub
End Module
' The example displays the following output:
'       Sorting using the en-US culture:
'          able
'          Æble
'          ångström
'          apple
'          Visual Studio
'          Windows
'       
'       Sorting using the sv-SE culture:
'          able
'          Æble
'          apple
'          Windows
'          Visual Studio
'          ångström
```

Сравнения без учета регистра, где используются текущий язык и региональные параметры, выполняются так же, как сравнения с учетом языка и региональных параметров с той разницей, что регистр игнорируется в соответствии с правилами текущего языка и региональных параметров потока. Это поведение может также проявляться в порядке сортировки. 

Сравнения, использующие семантику текущего языка и региональных параметров, используются по умолчанию для следующих методов.

* Перегрузки [String](xref:System.String) `Compare`, не включающие параметр [StringComparison](xref:System.StringComparison).

* Перегрузки [String.CompareTo](xref:System.String.CompareTo(System.String)).

* Метод по умолчанию [String.StartsWith(String)](xref:System.String.StartsWith(System.String)). 

* Метод по умолчанию [String.EndsWith(String)](xref:System.String.EndsWith(System.String)).

* Перегрузки [String](xref:System.String) `IndexOf`, принимающие в качестве параметра поиска [String](xref:System.String) и не имеющие параметра [StringComparison](xref:System.StringComparison).

* Перегрузки [String](xref:System.String) `LastIndexOf`, принимающие в качестве параметра поиска [String](xref:System.String) и не имеющие параметра [StringComparison](xref:System.StringComparison).

В любом случае рекомендуется вызвать перегрузку, имеющую параметр [StringComparison](xref:System.StringComparison), чтобы сделать назначение вызова метода очевидным. 

При лингвистической интерпретации нелингвистических строковых данных, а также если строковые данные определенного языка и региональных параметров интерпретируются с использованием правил другого языка, могут возникать малозаметные и не столь малозаметные ошибки. Типичный пример — проблема турецкого I.

Почти во всех латинских алфавитах, включая американский английский, символ i (\u0069) является строчной версией символа I (\u0049). Это правило учета регистра быстро становится значением по умолчанию для тех, кто программирует для этих языков. Однако в турецком алфавите (tr-TR) используется I с точкой — İ (\u0130), которая является прописной версией i. В турецком языке также есть строчная i без точки, ı (\u0131), прописной для которой является I. Эта же особенность имеется и в азербайджанском языке ("az").

Таким образом, допущения о прописной версии буквы i или строчной версии буквы I не являются правильными для всех языков. При использовании перегрузок по умолчанию для сравнения строк они будут меняться в зависимости от языков и региональных параметров. Если сравниваются нелингвистические данные, при использовании перегрузок по умолчанию может быть получен нежелательный результат, как показывает следующий пример с попыткой сравнить строки file и FILE без учета регистра.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fileUrl = "file";
      Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                       fileUrl.StartsWith("FILE", true, null));
      Console.WriteLine();

      Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                        fileUrl.StartsWith("FILE", true, null));
   }
}
// The example displays the following output:
//       Culture = English (United States)
//       (file == FILE) = True
//       
//       Culture = Turkish (Turkey)
//       (file == FILE) = False
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fileUrl = "file"
      Thread.CurrentThread.CurrentCulture = New CultureInfo("en-US")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                       fileUrl.StartsWith("FILE", True, Nothing))
      Console.WriteLine()

      Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                        fileUrl.StartsWith("FILE", True, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Culture = English (United States)
'       (file == FILE) = True
'       
'       Culture = Turkish (Turkey)
'       (file == FILE) = False
```

Это сравнение может вызвать значительные проблемы, если язык и региональные параметры случайно использовались в конфиденциальных параметрах, как показано в следующем примере. Вызов метода, например `IsFileURI("file:")`, возвращает значение `true`, если текущий язык — американский английский, и значение `false`, если текущий язык — турецкий. Следовательно, в системах на турецком языке кто-то может попытаться обойти механизмы безопасности, блокирующие доступ к URI без учета регистра, которые начинаются с текста «FILE:».

```csharp
public static bool IsFileURI(String path) 
{
   return path.StartsWith("FILE:", true, null);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
   Return path.StartsWith("FILE:", True, Nothing)
End Function
```

В этом случае, поскольку «file:» должен интерпретироваться как нелингвистический идентификатор без учета языка и региональных параметров, нужно писать код, как показано в следующем примере.

```csharp
public static bool IsFileURI(string path) 
{
   return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
    Return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase)
End Function
```

## <a name="ordinal-string-operations"></a>Порядковые операции со строками

Указание значения [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) или [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) в вызове метода является признаком нелингвистического сравнения, в котором признаки естественного языка игнорируются. Методы, которые вызываются с этими значениями [StringComparison](xref:System.StringComparison), принимают решения о строковых операциях на основе простых байтовых сравнений, а не таблиц регистров или эквивалентности, которые параметризуются языком и региональными параметрами. В большинстве случаев такой подход наиболее соответствует предполагаемой интерпретации строк, ускоряя выполнение кода и делая его более надежным. 

Порядковые сравнения — это сравнения строк, в которых каждый байт каждой строки сравнивается без лингвистической интерпретации; например, windows не равно Windows. Используйте такое сравнение, когда контекст определяет, что строки должны точно совпадать, или требует использования консервативной политики соответствия. Кроме того, порядковое сравнение — это самая быстрая операция сравнения, потому что при расчете результата не применяются лингвистические правила.

Строки в .NET могут содержать внедренные символы NULL. Одним из очевидных различий между порядковым сравнением и сравнением с учетом языка и региональных параметров (включая сравнения, в которых используется инвариантный язык и региональные параметры) является различие в обработке внедренных символов null в строке. Эти символы игнорируются при использовании методов [String](xref:System.String) `Compare` и [String](xref:System.String) `Equals` для сравнений с учетом языка и региональных параметров (включая сравнения, использующие инвариантный язык). В результате в сравнениях с учетом языка и региональных параметров строки, содержащие внедренные символы null, считаются равными строкам, которые таких символов не содержат. 

> [!IMPORTANT]
> Несмотря на то, что в методах сравнения строк не учитываются внедренные символы NULL, методы поиска строк, такие как [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)) и [String.StartsWith](xref:System.String.StartsWith(System.String)), эти символы учитывают. 

В следующем примере выполняется сравнение с учетом языка и региональных параметров строки Aa с аналогичной строкой, содержащей несколько внедренных символов null между А и а, и показано, почему две строки рассматриваются как равные. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string str1 = "Aa";
      string str2 = "A" + new String('\u0000', 3) + "a";
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                        str1, ShowBytes(str1), str2, ShowBytes(str2));
      Console.WriteLine("   With String.Compare:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.InvariantCulture));

      Console.WriteLine("   With String.Equals:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.InvariantCulture));
   }

   private static string ShowBytes(string str)
   {
      string hexString = String.Empty;
      for (int ctr = 0; ctr < str.Length; ctr++)
      {
         string result = String.Empty;
         result = Convert.ToInt32(str[ctr]).ToString("X4");
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2);
         hexString += result;
      }
      return hexString.Trim();
   }
}
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Current Culture: 0
//          Invariant Culture: 0
//       With String.Equals:
//          Current Culture: True
//          Invariant Culture: True
```

```vb
Module Example
   Public Sub Main()
      Dim str1 As String = "Aa"
      Dim str2 As String = "A" + New String(Convert.ToChar(0), 3) + "a"
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                        str1, ShowBytes(str1), str2, ShowBytes(str2))
      Console.WriteLine("   With String.Compare:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.InvariantCulture))

      Console.WriteLine("   With String.Equals:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.InvariantCulture))
   End Sub

   Private Function ShowBytes(str As String) As String
      Dim hexString As String = String.Empty
      For ctr As Integer = 0 To str.Length - 1
         Dim result As String = String.Empty
         result = Convert.ToInt32(str.Chars(ctr)).ToString("X4")
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2)
         hexString += result
      Next
      Return hexString.Trim()
   End Function
End Module
```

Однако строки не считаются равными, если выполняется порядковое сравнение, как показано в следующем примере.

```csharp
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                  str1, ShowBytes(str1), str2, ShowBytes(str2));
Console.WriteLine("   With String.Compare:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Compare(str1, str2, StringComparison.Ordinal));

Console.WriteLine("   With String.Equals:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Equals(str1, str2, StringComparison.Ordinal));
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Ordinal: 97
//       With String.Equals:
//          Ordinal: False
```

```vb
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                  str1, ShowBytes(str1), str2, ShowBytes(str2))
Console.WriteLine("   With String.Compare:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Compare(str1, str2, StringComparison.Ordinal))

Console.WriteLine("   With String.Equals:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Equals(str1, str2, StringComparison.Ordinal))
' The example displays the following output:
'    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
'       With String.Compare:
'          Ordinal: 97
'       With String.Equals:
'          Ordinal: False
```

Порядковые сравнения без учета регистра — это следующий наиболее консервативной подход к решению задачи. В этих сравнениях почти всегда игнорируется регистр. Так, windows совпадает с Windows. При работе с символами ASCII эта политика эквивалентна сравнению [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) за исключением того, что стандартные правила регистра ASCII игнорируются. Следовательно, любой символ в последовательности [A, Z] (\u0041–\u005A) соответствует соответствующему символу в последовательности [a, z] (\u0061–\007A). Правила регистра за пределами диапазона ASCII используют таблицы инвариантного языка. Поэтому следующее сравнение

```csharp
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase);
```

```vb
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase)
```

эквивалентно следующему сравнению (но выполняется быстрее): 

```csharp
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal);
```

```vb
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal)
```

Эти сравнения по-прежнему выполняются очень быстро.

И [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), и [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) используют двоичные значения непосредственно и лучше всего подходят для сопоставления. При отсутствии точной информации о параметрах сравнения используйте одно из этих двух значений. Однако, поскольку они выполняют побайтовое сравнение, лингвистическая сортировка (как в словаре английского языка) не выполняется, однако используется двоичный порядок сортировки. В большинстве случаев для пользователя эти результаты будут выглядеть странно.

Порядковая семантика используется по умолчанию для перегрузок [String](xref:System.String) `Equals`, которые не содержат аргумент [StringComparison](xref:System.StringComparison) (включая оператор равенства). В любом случае рекомендуется вызвать перегрузку, содержащую параметр [StringComparison](xref:System.StringComparison).

### <a name="string-operations-that-use-the-invariant-culture"></a>Строковые операции, использующие инвариантный язык и региональные параметры

В сравнениях с инвариантным языком используется свойство [CompareInfo](xref:System.Globalization.CompareInfo), возвращаемое статическим свойством [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture). Это поведение одинаково во всех системах; оно преобразует любые символы за пределами своего диапазона в то, что оно считает эквивалентными инвариантными символами. Эта политика может пригодиться для реализации единого набора поведений строк в разных языках и региональных параметрах, однако часто это дает непредвиденные результаты.

Сравнения без учета регистра с инвариантным языком также используют статическое свойство [CompareInfo](xref:System.Globalization.CompareInfo), возвращаемое статическим свойством [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) для сведений сравнения. Любые различия регистров в этих преобразуемых символах игнорируются.

Объект [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) заставляет метод [String](xref:System.String) `Compare` интерпретировать определенные наборы символов как эквивалентные. Например, следующие элементы эквивалентны только в инвариантном языке.

InvariantCulture: a + ̊ = å

Латинская строчная буква А, а (\u0061), находясь рядом с объединяющим кольцом над символом "+ " ̊"(\u030a), интерпретируется как строчная латинская буква а с кольцом над ней, å (\u00e5). Как показано в следующем примере, это поведение отличается от порядкового сравнения.

```csharp
string separated = "\u0061\u030a";
string combined = "\u00e5";

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}",
                  separated, combined, 
                  String.Compare(separated, combined, 
                                 StringComparison.InvariantCulture) == 0);

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}",
                  separated, combined,
                  String.Compare(separated, combined, 
                                 StringComparison.Ordinal) == 0);
// The example displays the following output:
//    Equal sort weight of a° and å using InvariantCulture: True
//    Equal sort weight of a° and å using Ordinal: False 
```

```vb
Dim separated As String = ChrW(&h61) + ChrW(&h30a)
Dim combined As String = ChrW(&he5)

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _ 
                                 StringComparison.InvariantCulture) = 0)

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _
                                 StringComparison.Ordinal) = 0)
' The example displays the following output:
'    Equal sort weight of a° and å using InvariantCulture: True
'    Equal sort weight of a° and å using Ordinal: False
```

При интерпретации имен файлов, файлов cookie или чего-либо еще, где могут появляться такие сочетания, как å, порядковые сравнения по-прежнему являются наиболее понятным и подходящим поведением.

В целом в инвариантном языке очень мало свойств, которые могли бы сделать его полезным для сравнения. Он выполняет сравнения с учетом лингвистических параметров, что не позволяет гарантировать полную эквивалентность символов, однако не подходит для отображения на любом языке. Например, если к приложению прилагается крупный файл данных, содержащий список сортированных идентификаторов для отображения, добавление в этот список потребует вставки элементов с сортировкой в инвариантном стиле.

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a>Выбор элемента StringComparison для вызова своего метода

В следующей таблице приведено сопоставление семантического контекста строк элементу перечисления [StringComparison](xref:System.StringComparison).

Данные | Поведение | Соответствующее значение System.StringComparison
---- | -------- | -------------------------------------------
Внутренние идентификаторы с учетом регистра, идентификаторы с учетом регистра в таких стандартах, как XML и HTTP или параметры безопасности с учетом регистра. | Нелингвистические идентификаторы с точным соответствием байтов. | [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)
Внутренние идентификаторы без учета регистра, идентификаторы без учета регистра в таких стандартах, как XML и HTTP, пути к файлам, разделы реестра и значения, переменные среды, идентификаторы ресурсов (например, имена дескрипторов) или параметры безопасности без учета регистра. | Нелингвистический идентификатор, в котором регистр не учитывается. | [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)
Данные, отображаемые для пользователя, или пользовательский ввод в большинстве случаев. | Данные, требующие местных лингвистических правил. | [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) или [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)

## <a name="common-string-comparison-methods"></a>Общие методы сравнения строк

В следующих разделах описываются методы, которые чаще всего используются для сравнения строк.

### <a name="stringcompare"></a>String.Compare

Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Поскольку эта операция наиболее тесно связана с интерпретацией строк, необходимо изучить все экземпляры вызовов этого метода, чтобы определить, должны ли строки интерпретироваться с учетом текущего языка и региональных параметров, либо их нужно (символически) отделить от языка и региональных параметров. Обычно выбирается последнее, и тогда должно использоваться сравнение [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).

Класс [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo), возвращаемый свойством [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo), также включает метод [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)), предоставляющий большое количество соответствующих параметров (порядковый, игнорирование пробела, игнорирование типа каны и т. д.) посредством перечисления флага [CompareOptions](xref:System.Globalization.CompareOptions). 

### <a name="stringcompareto"></a>String.CompareTo

Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Сейчас этот метод не предлагает перегрузку, задающую тип [StringComparison](xref:System.StringComparison). Обычно возможно преобразовать этот метод в рекомендованную форму [String.Compare (String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)).

Типы, реализующие интерфейсы [IComparable](xref:System.IComparable) и [IComparable&lt;T&gt;](xref:System.IComparable%601), реализуют этот метод. Поскольку параметр [StringComparison](xref:System.StringComparison) не предлагается, реализация типов часто позволяет пользователю задать [StringComparer](xref:System.StringComparer) в своем конструкторе. В следующем примере определяется класс `FileName`, конструктор класса которого включает параметр [StringComparer](xref:System.StringComparer). Затем этот объект [StringComparer](xref:System.StringComparer) используется в методе `FileName.CompareTo`.

```csharp
using System;

public class FileName : IComparable
{
   string fname;
   StringComparer comparer; 

   public FileName(string name, StringComparer comparer)
   {
      if (String.IsNullOrEmpty(name))
         throw new ArgumentNullException("name");

      this.fname = name;

      if (comparer != null)
         this.comparer = comparer;
      else
         this.comparer = StringComparer.OrdinalIgnoreCase;
   }

   public string Name
   {
      get { return fname; }
   }

   public int CompareTo(object obj)
   {
      if (obj == null) return 1;

      if (! (obj is FileName))
         return comparer.Compare(this.fname, obj.ToString());
      else
         return comparer.Compare(this.fname, ((FileName) obj).Name);
   }
}
```

```vb
Public Class FileName : Implements IComparable
   Dim fname As String
   Dim comparer As StringComparer 

   Public Sub New(name As String, comparer As StringComparer)
      If String.IsNullOrEmpty(name) Then
         Throw New ArgumentNullException("name")
      End If

      Me.fname = name

      If comparer IsNot Nothing Then
         Me.comparer = comparer
      Else
         Me.comparer = StringComparer.OrdinalIgnoreCase
      End If      
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return fname
      End Get   
   End Property

   Public Function CompareTo(obj As Object) As Integer _
          Implements IComparable.CompareTo
      If obj Is Nothing Then Return 1

      If Not TypeOf obj Is FileName Then
         obj = obj.ToString()
      Else
         obj = CType(obj, FileName).Name
      End If         
      Return comparer.Compare(Me.fname, obj)
   End Function
End Class
```

### <a name="stringequals"></a>String.Equals

Интерпретация по умолчанию: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).

Класс [String](xref:System.String) позволяет выполнить проверку на равенство, вызвав статические перегрузки метода `Equals` или перегрузки экземпляров. Кроме того, можно воспользоваться оператором статического равенства. Перегрузки и оператор используют порядковое сравнение по умолчанию. Однако рекомендуется вызывать перегрузку, которая явно задает тип [StringComparison](xref:System.StringComparison), даже если требуется выполнить порядковое сравнение. Это упрощает поиск кода для интерпретации определенной строки. 

### <a name="stringtoupper-and-stringtolower"></a>String.ToUpper и String.ToLower

Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Следует соблюдать осторожность, используя эти методы, поскольку принудительное преобразование строки в нижний или верхний регистр часто используется в качестве незначительной нормализации для сравнения строк независимо от регистра. В этом случае целесообразно выполнить сравнение без учета регистра. 

Также доступны методы [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) и [String.ToLowerInvariant](xref:System.String.ToLowerInvariant). [ToUpperInvariant](xref:System.String.ToUpperInvariant) — это стандартный способ нормализации регистра. Сравнения, выполненные с помощью [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase), с точки зрения поведения представляют собой комбинацию из двух вызовов: вызов [ToUpperInvariant](xref:System.String.ToUpperInvariant) в обоих аргументах строки и выполнение сравнения с использованием [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).

Также доступны перегрузки для преобразования в верхний и нижний регистр в конкретном языке. Для этого передается объект [CultureInfo](xref:System.Globalization.CultureInfo), представляющий этот язык для метода.

### <a name="chartoupper-and-chartolower"></a>Char.ToUpper и Char.ToLower

Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Эти методы работают аналогично методам [String.ToUpper](xref:System.String.ToUpper) и [String.ToLower](xref:System.String.ToLower), описанным выше.

### <a name="stringstartswith-and-stringendswith"></a>String.StartsWith и String.EndsWith

Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

По умолчанию оба этих метода выполняют сравнение с учетом языка и региональных параметров.

### <a name="stringindexof-and-stringlastindexof"></a>String.IndexOf и String.LastIndexOf

Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Перегрузки этих методов по умолчанию выполняют сравнения непоследовательно. Все методы [String](xref:System.String) `IndexOf` и [String](xref:System.String) `LastIndexOf`, включающие параметр [Char](xref:System.Char), выполняют порядковое сравнение, однако методы [String](xref:System.String) `IndexOf` и [String`](xref:System.String) `LastIndexOf] по умолчанию, которые включают параметр [String](xref:System.String), выполняют сравнение с учетом языка и региональных параметров. 

Если нужно вызвать метод ` `IndexOf` or `LastIndexOf и передать ему строку для определения ее местоположения в текущем экземпляре, рекомендуется вызвать перегрузку, которая явно задает тип [StringComparison](xref:System.StringComparison). Перегрузки, включающие аргумент [Char](xref:System.Char), не позволяют задать тип [StringComparison](xref:System.StringComparison).

## <a name="methods-that-perform-string-comparison-indirectly"></a>Методы, сравнивающие строки опосредованно

Некоторые нестроковые методы, основным назначением которых является сравнение строк, используют тип [StringComparer](xref:System.StringComparer). Класс [StringComparer](xref:System.StringComparer) включает четыре статических свойства, возвращающих экземпляры [StringComparer](xref:System.StringComparer), методы `Compare` которых выполняют следующие типы сравнения строк.

* Сравнения строк с учетом языка и региональных параметров с использованием текущего языка и региональных параметров. Этот объект [StringComparer](xref:System.StringComparer) возвращается свойством [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture).

* Сравнение без учета регистра с использованием текущего языка и региональных параметров. Этот объект [StringComparer](xref:System.StringComparer) возвращается свойством [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase).

* Порядковое сравнение. Этот объект [StringComparer](xref:System.StringComparer) возвращается свойством [StringComparer.Ordinal](xref:System.StringComparer.Ordinal). 

* Порядковое сравнение без учета регистра. Этот объект [StringComparer](xref:System.StringComparer) возвращается свойством [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase).

### <a name="arraysort-and-arraybinarysearch"></a>Array.Sort и Array.BinarySearch

Интерпретация по умолчанию: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

При хранении любых данных в коллекции или считывании сохраненных данных из файла или базы данных в коллекцию изменение текущего языка и региональных параметров может сделать недействительными инварианты этой коллекции. Метод [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) предполагает, что элементы в массиве, поиск которых необходимо выполнить, уже сортированы. Чтобы отсортировать любой строковый элемент в массиве, метод [Array.Sort](xref:System.Array.Sort(System.Array)) вызывает метод [String] `Compare` для упорядочивания отдельных элементов. Использовать средство сравнения с учетом языка и региональных параметров может быть опасно, если язык и региональные параметры изменяются в период между сортировкой массива и поиском в содержимом этого массива. Например, в следующем коде для хранения и извлечения данных используется средство сравнения, которое неявно предоставляется свойством `Thread.CurrentThread.CurrentCulture`. Если язык и региональные параметры могут измениться между вызовом `StoreNames` и `DoesNameExist` и особенно если содержимое массива сохраняется в период между вызовами этих двух методов, двоичный поиск может завершиться ошибкой. 

```csharp
// Incorrect.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names); // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name) >= 0);  // Line B.
}
```

```vb
' Incorrect.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names)          ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name) >= 0      ' Line B.
End Function
```

Рекомендуемый вариант показан в следующем примере, где один и тот же метод порядкового сравнения (без учета языка и региональных параметров) используется для сортировки массива и поиска в нем. Измененный код отражается в строках, помеченных в этих двух примерах как `Line A` и `Line B`.

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.Ordinal);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.Ordinal) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.Ordinal)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.Ordinal) >= 0      ' Line B.
End Function
```

Если эти данные сохраняются и перемещаются в разных языках, а для представления этих данных пользователю используется сортировка, целесообразно использовать `StringComparison.InvariantCulture`, действующий с учетом лингвистических правил и, следовательно, повышающий качество выводимых пользователю данных, но при этом не подверженный влиянию изменений в языке и региональных параметрах. В следующем примере два предыдущих примера изменяются так, чтобы для сортировки массива и поиска в нем использовался инвариантный язык.

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.InvariantCulture);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.InvariantCulture) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.InvariantCulture)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.InvariantCulture) >= 0      ' Line B.
End Function
```

### <a name="collections-example-hashtable-constructor"></a>Пример коллекций: доступный для кэширования конструктор

Хэширование строк — это второй пример операции, на которую влияет способ сравнения строк. 

В следующем примере создается экземпляр объекта [Hashtable](xref:System.Collections.Hashtable) путем передачи его объекту [StringComparer](xref:System.StringComparer), который возвращается свойством [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase). Поскольку класс [StringComparer](xref:System.StringComparer), который является производным от [StringComparer](xref:System.StringComparer), реализует интерфейс [IEqualityComparer](xref:System.Collections.IEqualityComparer), его метод [GetHashCode](xref:System.Collections.IEqualityComparer) используется для вычисления хэш-кода строк в хэш-таблице.

```csharp
const int initialTableCapacity = 100;
Hashtable h;

public void PopulateFileTable(string directory)
{
   h = new Hashtable(initialTableCapacity, 
                     StringComparer.OrdinalIgnoreCase);

   foreach (string file in Directory.GetFiles(directory))
         h.Add(file, File.GetCreationTime(file));
}

public void PrintCreationTime(string targetFile)
{
   Object dt = h[targetFile];
   if (dt != null)
   {
      Console.WriteLine("File {0} was created at time {1}.",
         targetFile, 
         (DateTime) dt);
   }
   else
   {
      Console.WriteLine("File {0} does not exist.", targetFile);
   }
}
```

```vb
Const initialTableCapacity As Integer = 100
Dim h As Hashtable

Public Sub PopulateFileTable(dir As String)
   h = New Hashtable(initialTableCapacity, _
                     StringComparer.OrdinalIgnoreCase)

   For Each filename As String In Directory.GetFiles(dir)
      h.Add(filename, File.GetCreationTime(filename))
   Next                        
End Sub

Public Sub PrintCreationTime(targetFile As String)
   Dim dt As Object = h(targetFile)
   If dt IsNot Nothing Then
      Console.WriteLine("File {0} was created at {1}.", _
         targetFile, _
         CDate(dt))
   Else
      Console.WriteLine("File {0} does not exist.", targetFile)
   End If
End Sub  
```

## <a name="displaying-and-persisting-formatted-data"></a>Отображение и сохранение форматированных данных

При отображении нестроковых данных, например чисел, дат и времени, пользователям следует форматировать их с использованием параметров языка и региональных параметров пользователя. По умолчанию метод [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) и методы `ToString` числовых типов и типов даты и времени используют текущий язык потока для операций форматирования. Чтобы явно указать, что метод форматирования должен использовать текущий язык и региональные параметры, можно вызвать перегрузку метода форматирования, который имеет параметр provider, например [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) или [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), и передать ему свойство [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture). 

Нестроковые данные можно сохранить в виде двоичных или форматированных данных. Если решено сохранять данные в виде форматированных, нужно вызвать перегрузку метода форматирования, которая включает параметр *provider*, и передать ей свойство [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture). Инвариантный язык и региональные параметры предоставляют согласованный формат для форматированных данных независимо от языка, региональных параметров и компьютера. Напротив, сохранение форматированных данных с использованием языков и региональных параметров, отличающихся от инвариантных, имеет ряд ограничений. 

* Данные, вероятно, станут недоступными для использования после извлечения в системе с другим языком либо если пользователь текущей системы сменит текущий язык и попытается извлечь данные. 

* Свойства языка и региональных параметров на конкретном компьютере могут отличаться от стандартных значений. Пользователь может в любой момент настроить параметры отображения с учетом языка и региональных параметров. По этой причине форматированные данные, которые сохраняются в системе, могут стать недоступными для чтения после изменения настроек языка пользователем. Переносимость форматированных данных с одного компьютера на другой, вероятно, будет еще более ограниченной. 

* Международные, региональные и национальные стандарты, регулирующие форматирование чисел, дат и времени, со временем меняются, и эти изменения отражаются в обновлениях операционной системы. При изменении правил форматирования данные, форматированные с использованием старых правил, становятся недоступными для чтения. 

В следующем примере демонстрируется ограниченная переносимость в результате использования для сохранения данных форматирования с учетом языка и региональных параметров. В этом примере массив значений даты и времени сохраняется в файл. Данные форматируются с использованием правил английского языка (США). После того как приложение сменит текущий язык потока на французский (Швейцария), оно попытается прочитать сохраненные значения, используя правила форматирования текущей культуры. При попытке чтения двух элементов данных создается исключение [FormatException](xref:System.FormatException), а массив дат теперь содержит два неправильных элемента, равных [MinValue](xref:System.DateTime.MinValue). 

```csharp
using System;
using System.Globalization;
using System.IO;
using System.Text;
using System.Threading;

public class Example
{
   private static string filename = @".\dates.dat";

   public static void Main()
   {
      DateTime[] dates = { new DateTime(1758, 5, 6, 21, 26, 0), 
                           new DateTime(1818, 5, 5, 7, 19, 0), 
                           new DateTime(1870, 4, 22, 23, 54, 0),  
                           new DateTime(1890, 9, 8, 6, 47, 0), 
                           new DateTime(1905, 2, 18, 15, 12, 0) }; 
      // Write the data to a file using the current culture.
      WriteData(dates);
      // Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH");
      // Read the data using the current culture.
      DateTime[] newDates = ReadData();
      foreach (var newDate in newDates)
         Console.WriteLine(newDate.ToString("g"));
   }

   private static void WriteData(DateTime[] dates) 
   {
      StreamWriter sw = new StreamWriter(filename, false, Encoding.UTF8);    
      for (int ctr = 0; ctr < dates.Length; ctr++) {
         sw.Write("{0}", dates[ctr].ToString("g", CultureInfo.CurrentCulture));
         if (ctr < dates.Length - 1) sw.Write("|");   
      }      
      sw.Close();
   }

   private static DateTime[] ReadData() 
   {
      bool exceptionOccurred = false;

      // Read file contents as a single string, then split it.
      StreamReader sr = new StreamReader(filename, Encoding.UTF8);
      string output = sr.ReadToEnd();
      sr.Close();   

      string[] values = output.Split( new char[] { '|' } );
      DateTime[] newDates = new DateTime[values.Length]; 
      for (int ctr = 0; ctr < values.Length; ctr++) {
         try {
            newDates[ctr] = DateTime.Parse(values[ctr], CultureInfo.CurrentCulture);
         }
         catch (FormatException) {
            Console.WriteLine("Failed to parse {0}", values[ctr]);
            exceptionOccurred = true;
         }
      }      
      if (exceptionOccurred) Console.WriteLine();
      return newDates;
   }
}
// The example displays the following output:
//       Failed to parse 4/22/1870 11:54 PM
//       Failed to parse 2/18/1905 3:12 PM
//       
//       05.06.1758 21:26
//       05.05.1818 07:19
//       01.01.0001 00:00
//       09.08.1890 06:47
//       01.01.0001 00:00
//       01.01.0001 00:00
```

```vb
Imports System.Globalization
Imports System.IO
Imports System.Text
Imports System.Threading

Module Example
   Private filename As String = ".\dates.dat"

   Public Sub Main()
      Dim dates() As Date = { #5/6/1758 9:26PM#, #5/5/1818 7:19AM#, _ 
                              #4/22/1870 11:54PM#, #9/8/1890 6:47AM#, _ 
                              #2/18/1905 3:12PM# }
      ' Write the data to a file using the current culture.
      WriteData(dates)
      ' Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH")
      ' Read the data using the current culture.
      Dim newDates() As Date = ReadData()
      For Each newDate In newDates
         Console.WriteLine(newDate.ToString("g"))
      Next
   End Sub

   Private Sub WriteData(dates() As Date)
      Dim sw As New StreamWriter(filename, False, Encoding.Utf8)    
      For ctr As Integer = 0 To dates.Length - 1
         sw.Write("{0}", dates(ctr).ToString("g", CultureInfo.CurrentCulture))
         If ctr < dates.Length - 1 Then sw.Write("|")   
      Next      
      sw.Close()
   End Sub

   Private Function ReadData() As Date()
      Dim exceptionOccurred As Boolean = False

      ' Read file contents as a single string, then split it.
      Dim sr As New StreamReader(filename, Encoding.Utf8)
      Dim output As String = sr.ReadToEnd()
      sr.Close()   

      Dim values() As String = output.Split( {"|"c } )
      Dim newDates(values.Length - 1) As Date 
      For ctr As Integer = 0 To values.Length - 1
         Try
            newDates(ctr) = DateTime.Parse(values(ctr), CultureInfo.CurrentCulture)
         Catch e As FormatException
            Console.WriteLine("Failed to parse {0}", values(ctr))
            exceptionOccurred = True
         End Try
      Next      
      If exceptionOccurred Then Console.WriteLine()
      Return newDates
   End Function
End Module
' The example displays the following output:
'       Failed to parse 4/22/1870 11:54 PM
'       Failed to parse 2/18/1905 3:12 PM
'       
'       05.06.1758 21:26
'       05.05.1818 07:19
'       01.01.0001 00:00
'       09.08.1890 06:47
'       01.01.0001 00:00
'       01.01.0001 00:00
'
```

Однако если заменить свойство [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) на [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) в вызовах методов [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) и [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), хранимые данные даты и времени восстанавливаются успешно, как показано ниже.

```
// 06.05.1758 21:26
// 05.05.1818 07:19
// 22.04.1870 23:54
// 08.09.1890 06:47
// 18.02.1905 15:12
```

## <a name="see-also"></a>См. также

[Операции со строками](manipulating-strings.md)



<!--HONumber=Nov16_HO1-->


