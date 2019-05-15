---
title: Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы - руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 99d30d6c2b50569312ff2d732a34020ab29ce81c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595063"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы (руководство по программированию на C#)
В следующих примерах кода показано выполнение указанных ниже задач.  
  
- Получение шестнадцатеричного значения каждого символа в [string](../../../csharp/language-reference/keywords/string.md).  
  
- Получение [char](../../../csharp/language-reference/keywords/char.md), соответствующего каждому значению в шестнадцатеричной строке.  
  
- Преобразование шестнадцатеричного значения `string` в [int](../../../csharp/language-reference/keywords/int.md).  
  
- Преобразование шестнадцатеричного значения `string` в [float](../../../csharp/language-reference/keywords/float.md).  
  
- Преобразование массива [byte](../../../csharp/language-reference/keywords/byte.md) в шестнадцатеричное значение `string`.  
  
## <a name="example"></a>Пример  
 Результатом следующего примера является шестнадцатеричное значение каждого символа в `string`. Сначала выполняется разбор `string` до массива символов. Затем, чтобы получить числовое значение каждого символа, для каждого из них вызывается метод <xref:System.Convert.ToInt32%28System.Char%29>. В конце формат числа меняется на шестнадцатеричный в `string`.  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a>Пример  
 В этом примере анализируется `string` шестнадцатеричных значений и выводится символ, соответствующий каждому шестнадцатеричному значению. Сначала вызывается метод [Split(Char\[\])](xref:System.String.Split(System.Char[])) для получения каждого шестнадцатеричного значения как отдельной `string` в массиве. Затем вызывается метод <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>, который преобразует шестнадцатеричное значение в десятичное, представленное в [целое число](../../../csharp/language-reference/keywords/int.md). В примере показано два разных способа получения символа, соответствующего этому коду символа. В первом случае используется <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, который возвращает символ, соответствующий целочисленному аргументу, в виде `string`. По второму способу выполняется явное приведение `int` к [char](../../../csharp/language-reference/keywords/char.md).  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a>Пример  
 В этом примере показан еще один способ преобразования шестнадцатеричного `string` в целое число — с помощью метода <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> .  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано преобразование шестнадцатеричного `string` в [число с плавающей запятой](../../../csharp/language-reference/keywords/float.md) с помощью класса <xref:System.BitConverter?displayProperty=nameWithType> и метод <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано преобразование массива [байтов](../../../csharp/language-reference/keywords/byte.md) в шестнадцатеричную строку с помощью класса <xref:System.BitConverter?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a>См. также

- [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md)
- [Типы](../../../csharp/programming-guide/types/index.md)
- [Практическое руководство. Определение представления числового значения в строке](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
