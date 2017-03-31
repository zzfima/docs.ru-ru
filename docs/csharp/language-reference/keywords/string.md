---
title: "string (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- string
- string_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a616808a8e6ff5e259c503c0143db4b8f73bdef2
ms.lasthandoff: 03/13/2017

---
# <a name="string-c-reference"></a>string (Справочник по C#)
Тип `string` представляет последовательность, состоящую из нуля или более символов в кодировке Юникод. `string` — псевдоним для <xref:System.String> в .NET Framework.  
  
 Несмотря на то, что `string` представляет собой ссылочный тип, операторы равенства (`==` и`!=`) по определению сравнивают не ссылки, а значения объектов `string`. Это делает проверку равенства строк более интуитивно понятной. Например:  
  
```csharp  
  
      string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 Отображается значение True, а затем False, поскольку содержимое строк эквивалентно, однако `a` и `b` не относятся к одному и тому же экземпляру строки.  
  
 Оператор + объединяет строки:  
  
```csharp  
  
string a = "good " + "morning";  
```  
  
 При этом создается строковый объект, содержащий слова "good morning".  
  
 Строки *неизменяемы*, т. е. содержимое созданного строкового объекта изменить нельзя, хотя синтаксис выглядит так, будто это возможно. Например, при написании кода компилятор фактически создает новый строковый объект для хранения новой последовательности символов, а затем этот новый объект назначается b. После этого строка h может быть отправлена в мусор.  
  
```csharp  
  
      string b = "h";  
b += "ello";  
```  
  
 Оператор [] позволяет предоставить к отдельным символам `string` доступ только для чтения:  
  
```csharp  
  
      string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 Строковые литералы имеют тип `string` и могут быть записаны в двух формах: в кавычках или с @-quoted. Строковые литералы в кавычках заключаются в двойные кавычки ("):  
  
```csharp  
"good morning"  // a string literal  
```  
  
 Строковые литералы могут содержать любые символьные литералы. Escape-последовательности включены. В следующем примере escape-последовательность `\\` используется для получения обратной косой черты, `\u0066` — для получения буквы f, и `\n` — для получения новой строки.  
  
```  
  
      string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  Escape-код `\`u`dddd` (где `dddd` состоит из четырех цифр) представляет символ Юникода U+`dddd`. Также распознаются восьмизначные escape-коды Юникода: `\Udddddddd`.  
  
 Строковые литералы verbatim начинаются с @ и также заключаются в двойные кавычки. Пример:  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 Преимущество сток verbatim состоит в том, что escape-последовательности *не* обрабатываются, что позволяет легко написать, например, полное имя файла:  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 Чтобы добавить в строку @-quoted двойные кавычки, продублируйте этот символ:  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 Кроме того, символ @ применяется для использования ссылочных идентификаторов ([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)), представляющих собой ключевые слова C#.  
  
 Дополнительные сведения о строках в С# см. в разделе [Строки](../../../csharp/programming-guide/strings/index.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Рекомендации по использованию строк](http://msdn.microsoft.com/library/b9f0bf53-e2de-4116-8ce9-d4f91a1df4f7)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)   
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)   
 [Базовые операции со строками](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)   
 [Создание новых строк](http://msdn.microsoft.com/library/06fdf123-2fac-4459-8904-eb48ab908a30)   
 [Таблица форматирования числовых результатов](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)
