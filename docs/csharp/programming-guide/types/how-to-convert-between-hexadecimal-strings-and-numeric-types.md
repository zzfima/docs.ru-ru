---
title: "Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5852e79f551ce88e0ca54de159abbc222d769234
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы (Руководство по программированию на C#)
В следующих примерах кода показано выполнение указанных ниже задач.  
  
-   Получение шестнадцатеричного значения каждого символа в [string](../../../csharp/language-reference/keywords/string.md).  
  
-   Получение [char](../../../csharp/language-reference/keywords/char.md), соответствующего каждому значению в шестнадцатеричной строке.  
  
-   Преобразование шестнадцатеричного значения `string` в [int](../../../csharp/language-reference/keywords/int.md).  
  
-   Преобразование шестнадцатеричного значения `string` в [float](../../../csharp/language-reference/keywords/float.md).  
  
-   Преобразование массива [byte](../../../csharp/language-reference/keywords/byte.md) в шестнадцатеричное значение `string`.  
  
## <a name="example"></a>Пример  
 Результатом следующего примера является шестнадцатеричное значение каждого символа в `string`. Сначала выполняется разбор `string` до массива символов. Затем для каждого символа вызывается метод <xref:System.Convert.ToInt32%28System.Char%29>, чтобы получить его числовое значение. В конце формат числа меняется на шестнадцатеричный в `string`.  
  
 [!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере анализируется `string` шестнадцатеричных значений и выводится символ, соответствующий каждому шестнадцатеричному значению. Сначала вызывается метод [Split(Char\[\])](xref:System.String.Split(System.Char[])) для получения каждого шестнадцатеричного значения как отдельной `string` в массиве. Затем вызывается метод <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> для преобразования шестнадцатеричного значения в десятичное, представленное в формате [int](../../../csharp/language-reference/keywords/int.md). В примере показано два разных способа получения символа, соответствующего этому коду символа. В первом случае используется <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, который возвращает символ, соответствующий целочисленному аргументу в виде `string`. По второму способу выполняется явное приведение `int` к [char](../../../csharp/language-reference/keywords/char.md).  
  
 [!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере показан еще один способ преобразования шестнадцатеричного `string` в целое число путем вызова метода <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>.  
  
 [!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано преобразование шестнадцатеричного `string` в [float](../../../csharp/language-reference/keywords/float.md) с помощью класса <xref:System.BitConverter?displayProperty=fullName> и метода <xref:System.Int32.Parse%2A?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано преобразование массива [byte](../../../csharp/language-reference/keywords/byte.md) в шестнадцатеричную строку с помощью класса <xref:System.BitConverter?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## <a name="see-also"></a>См. также  
 [Строки стандартных числовых форматов](http://msdn.microsoft.com/library/580e57eb-ac47-4ffd-bccd-3a1637c2f467)   
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [Практическое руководство. Определение представления числового значения в строке](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)

