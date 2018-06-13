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
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="7d8cb-102">Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d8cb-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="7d8cb-103">Этот пример преобразует шестнадцатеричную строку в целое число, используя <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="7d8cb-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="7d8cb-104">Чтобы преобразовать число в шестнадцатеричную строку</span><span class="sxs-lookup"><span data-stu-id="7d8cb-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="7d8cb-105">Использование <xref:System.Convert.ToInt32(System.String,System.Int32)> метода для преобразования в base-16 в целое число.</span><span class="sxs-lookup"><span data-stu-id="7d8cb-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="7d8cb-106">Первый аргумент <xref:System.Convert.ToInt32(System.String,System.Int32)> метод является строка для преобразования.</span><span class="sxs-lookup"><span data-stu-id="7d8cb-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="7d8cb-107">Второй аргумент описывает, какая база, число, представленное в; шестнадцатеричное является основанием 16.</span><span class="sxs-lookup"><span data-stu-id="7d8cb-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- <span data-ttu-id="7d8cb-108">Обратите внимание, что шестнадцатеричная строка имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="7d8cb-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="7d8cb-109">Оно не может включать `&h` префикс.</span><span class="sxs-lookup"><span data-stu-id="7d8cb-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="7d8cb-110">Оно не может включать `_` разделитель групп.</span><span class="sxs-lookup"><span data-stu-id="7d8cb-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="7d8cb-111">Если префикс или цифровой разделитель отсутствует, вызов <xref:System.Convert.ToInt32(System.String,System.Int32)> вызывает исключение <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="7d8cb-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d8cb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7d8cb-112">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
