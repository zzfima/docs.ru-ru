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
ms.openlocfilehash: c8ef615b6874642fa9ad1b22fe9d7f7745d4ffde
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201005"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="ddbb2-102">Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddbb2-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>
<span data-ttu-id="ddbb2-103">Этот пример преобразует шестнадцатеричную строку в целое число, используя <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="ddbb2-104">Для преобразования шестнадцатеричной строки в число</span><span class="sxs-lookup"><span data-stu-id="ddbb2-104">To convert a hexadecimal string to a number</span></span>  
  
-   <span data-ttu-id="ddbb2-105">Используйте <xref:System.Convert.ToInt32(System.String,System.Int32)> метод преобразуемое число, представленное в base-16 в целое число.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>  
  
     <span data-ttu-id="ddbb2-106">Первый аргумент <xref:System.Convert.ToInt32(System.String,System.Int32)> метод является строка для преобразования.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="ddbb2-107">Второй аргумент описывает базовый номер выражается в; шестнадцатеричное является основанием 16.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>  
  
     [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]  

- <span data-ttu-id="ddbb2-108">Обратите внимание на то, что шестнадцатеричная строка имеет следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="ddbb2-108">Note that the hexadecimal string has the following restrictions:</span></span>

   - <span data-ttu-id="ddbb2-109">Он не может включать `&h` префикс.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-109">It cannot include the `&h` prefix.</span></span>
   - <span data-ttu-id="ddbb2-110">Он не может включать `_` разделитель разрядов.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-110">It cannot include the `_` digit separator.</span></span>

   <span data-ttu-id="ddbb2-111">Если префикс или разделителя разрядов отсутствует, вызов <xref:System.Convert.ToInt32(System.String,System.Int32)> вызывает метод <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="ddbb2-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddbb2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ddbb2-112">See also</span></span>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
