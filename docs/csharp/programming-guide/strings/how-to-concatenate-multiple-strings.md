---
title: "Практическое руководство. Сцепка нескольких строк (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a>Практическое руководство. Сцепка нескольких строк (Руководство по программированию на C#)
*Объединение* подразумевает добавление одной строки к концу другой. При объединении строковых литералов или строковых констант с помощью оператора `+` компилятор создает одну строку. Объединение не осуществляется во время выполнения. Тем не менее строковые переменные могут быть объединены только во время выполнения. В этом случае необходимо понимать влияние различных подходов на общую производительность.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как разделить длинный строковый литерал на маленькие строки для повышения удобочитаемости исходного кода. Эти части будут объединены в одну строку во время компиляции. Независимо от числа включаемых в операцию строк, производительность во время выполнения снижаться не будет.  
  
 [!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a>Пример  
 Для объединения строковых переменных можно использовать операторы `+` или `+=`, а также методы <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> или <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>. Оператор `+` прост в использовании и позволяет получить интуитивно понятный код. Даже если в одном выражении используется несколько операторов +, содержимое строки копируется только один раз. Однако если эта операция повторяется многократно, например в цикле, возможно ухудшение эффективности. Например, изучите следующий код:  
  
 [!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  В операциях объединения строк компилятор C# обрабатывает строки NULL так же, как и пустые строки, однако при этом не преобразует значение исходной строки NULL.  
  
 Если вы не объединяете большое число строк (например, в цикле), влияние на производительность будет незначительным. Это справедливо также для методов <xref:System.String.Concat%2A?displayProperty=fullName> и <xref:System.String.Format%2A?displayProperty=fullName>.  
  
 Тем не менее, если производительность имеет первоочередное значение, для объединения строк всегда следует использовать класс <xref:System.Text.StringBuilder>. В следующем коде для объединения строк используется метод <xref:System.Text.StringBuilder.Append%2A> класса <xref:System.Text.StringBuilder>, не дающий того эффекта цепочки, который характерен для оператора `+`.  
  
 [!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.String>   
 <xref:System.Text.StringBuilder>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)

