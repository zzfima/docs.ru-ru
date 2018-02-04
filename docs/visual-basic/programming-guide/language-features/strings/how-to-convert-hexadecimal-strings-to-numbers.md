---
title: "Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)"
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: petrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: c35ac615e3f87710f934a1cf66e6546625298bd0
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)
Этот пример преобразует шестнадцатеричную строку в целое число, используя <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> метод.  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Чтобы преобразовать число в шестнадцатеричную строку  
  
-   Использование <xref:System.Convert.ToInt32(System.String,System.Int32)> метода для преобразования в base-16 в целое число.  
  
     Первый аргумент <xref:System.Convert.ToInt32(System.String,System.Int32)> метод является строка для преобразования. Второй аргумент описывает, какая база, число, представленное в; шестнадцатеричное является основанием 16.  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- Обратите внимание, что шестнадцатеричная строка имеет следующие ограничения:

   - Оно не может включать `&h` префикс.
   - Оно не может включать `_` разделитель групп.

   Если префикс или цифровой разделитель отсутствует, вызов <xref:System.Convert.ToInt32(System.String,System.Int32)> вызывает исключение <xref:System.FormatException>.

## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
