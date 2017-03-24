---
title: "string (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "string"
  - "string_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "строки [C#], справочник"
  - "@ - строковый литерал"
  - "строковые литералы [C#]"
  - "string - ключевое слово [C#]"
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# string (Справочник по C#)
Тип `string` представляет последовательность из нуля или более символов в кодировке Юникод.  Тип `string` — это псевдоним для типа <xref:System.String> платформы .NET Framework.  
  
 Несмотря на то, что тип `string` является ссылочным типом, операторы равенства \(`==` и `!=`\) определены для сравнения значений объектов типа `string`, а не ссылок.  Это упрощает проверку равенства строк.  Например:  
  
```c#  
  
      string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 В этом примере отображается "True", а затем "False", поскольку содержимое строк одинаково, но `a` и `b` не ссылаются на один и тот же экземпляр строки.  
  
 Оператор \+ служит для объединения строк.  
  
```c#  
  
string a = "good " + "morning";  
```  
  
 В данном примере создается строковый объект, содержащий текст "good morning".  
  
 Строки являются *неизменяемыми*: содержимое строкового объекта невозможно изменить после создания объекта, хотя из\-за синтаксиса изменения кажутся возможными.  Например, при написании этого кода компилятор на самом деле создает новый строковый объект для новой последовательности знаков, и этот новый объект получает значение "b".  Затем строку "h" можно применять для сборки мусора.  
  
```c#  
  
      string b = "h";  
b += "ello";  
```  
  
 Оператор \[\] служит для доступа только для чтения к отдельным знакам объекта `string`.  
  
```c#  
  
      string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 Строковые литералы имеют тип `string` и могут быть написаны в двух формах: в кавычках и в кавычках с @.  Строковые литералы в кавычках заключены в двойные кавычки \("\).  
  
```c#  
"good morning"  // a string literal  
```  
  
 Строковые литералы могут содержать любые символьные литералы.  Escape\-последовательности также поддерживаются.  В следующем примере используется escape\-последовательность `\\` для обратной косой черты, `\u0066` для буквы "f" и `\n` для перехода на новую строку.  
  
```  
  
      string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  Escape\-код `\`u`dddd` \(где `dddd` — четырехзначное число\) представляет знак Юникода U\+`dddd`.  Также распознаются восьмизначные escape\-коды Юникода: `\Udddddddd`.  
  
 Литералы из точных сток начинаются со знака @ и заключены в двойные кавычки.  Например:  
  
```c#  
@"good morning"  // a string literal  
```  
  
 Преимущество точных сток заключается в том, что escape\-последовательности *не* обрабатывается, благодаря чему можно удобно написать, например, полное имя и путь файла:  
  
```c#  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 Чтобы включить знак двойной кавычки в строку в кавычках с @, следует использовать знак кавычек дважды:  
  
```c#  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 Знак @ также можно применять для использования указанных идентификаторов \([\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)\), являющихся ключевыми словами C\#.  
  
 Дополнительные сведения о строках в C\# см. в разделе [Строки](../../../csharp/programming-guide/strings/index.md).  
  
## Пример  
 [!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендации по использованию строк](../Topic/Best%20Practices%20for%20Using%20Strings%20in%20the%20.NET%20Framework.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)   
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)   
 [Основные операции со строками](../Topic/Basic%20String%20Operations%20in%20the%20.NET%20Framework.md)   
 [Создание новых строк](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)