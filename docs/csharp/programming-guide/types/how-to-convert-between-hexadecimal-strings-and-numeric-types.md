---
title: Руководство по программированию на C#. Преобразование шестнадцатеричных значений из строкового типа в числовой тип
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 0e1f6ad2606b367d369c1c644c947831b2aa8289
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75698525"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>Руководство по программированию на C#. Преобразование шестнадцатеричных значений из строкового типа в числовой тип
В следующих примерах кода показано выполнение указанных ниже задач.  
  
- Получение шестнадцатеричного значения каждого символа в [string](../../language-reference/builtin-types/reference-types.md).  
  
- Получение [char](../../language-reference/builtin-types/char.md), соответствующего каждому значению в шестнадцатеричной строке.  
  
- Преобразование шестнадцатеричного значения `string` в [int](../../language-reference/builtin-types/integral-numeric-types.md).  
  
- Преобразование шестнадцатеричного значения `string` в [float](../../language-reference/builtin-types/floating-point-numeric-types.md).  
  
- Преобразование массива [byte](../../language-reference/builtin-types/integral-numeric-types.md) в шестнадцатеричное значение `string`.  
  
## <a name="example"></a>Пример  
 Результатом следующего примера является шестнадцатеричное значение каждого символа в `string`. Сначала выполняется разбор `string` до массива символов. Затем, чтобы получить числовое значение каждого символа, для каждого из них вызывается метод <xref:System.Convert.ToInt32%28System.Char%29>. В конце формат числа меняется на шестнадцатеричный в `string`.  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a>Пример  
 В этом примере анализируется `string` шестнадцатеричных значений и выводится символ, соответствующий каждому шестнадцатеричному значению. Сначала вызывается метод [Split(Char\[\])](xref:System.String.Split(System.Char[])) для получения каждого шестнадцатеричного значения как отдельной `string` в массиве. Затем вызывается метод <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>, который преобразует шестнадцатеричное значение в десятичное, представленное в [целое число](../../language-reference/builtin-types/integral-numeric-types.md). В примере показано два разных способа получения символа, соответствующего этому коду символа. В первом случае используется <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, который возвращает символ, соответствующий целочисленному аргументу, в виде `string`. По второму способу выполняется явное приведение `int` к [char](../../language-reference/builtin-types/char.md).  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a>Пример  
 В этом примере показан еще один способ преобразования шестнадцатеричного `string` в целое число — с помощью метода <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> .  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано преобразование шестнадцатеричного `string` в [число с плавающей запятой](../../language-reference/builtin-types/floating-point-numeric-types.md) с помощью класса <xref:System.BitConverter?displayProperty=nameWithType> и метод <xref:System.UInt32.Parse%2A?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано преобразование массива [байтов](../../language-reference/builtin-types/integral-numeric-types.md) в шестнадцатеричную строку с помощью класса <xref:System.BitConverter?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="see-also"></a>См. также

- [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md)
- [Типы](./index.md)
- [Определение представления числового значения в строке](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
