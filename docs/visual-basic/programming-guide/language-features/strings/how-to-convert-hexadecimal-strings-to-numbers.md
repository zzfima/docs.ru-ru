---
title: Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af0e6c1e30c116709ed98240de7bf3471fa842d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648646"
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
