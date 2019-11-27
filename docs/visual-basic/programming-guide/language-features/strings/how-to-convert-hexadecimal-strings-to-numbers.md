---
title: Практическое руководство. Преобразование шестнадцатеричных строк в числа
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347176"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a><span data-ttu-id="678dd-102">Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="678dd-102">How to: Convert Hexadecimal Strings to Numbers (Visual Basic)</span></span>

<span data-ttu-id="678dd-103">В этом примере шестнадцатеричная строка преобразуется в целое число с помощью метода <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="678dd-103">This example converts a hexadecimal string to an integer using the <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method.</span></span>

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a><span data-ttu-id="678dd-104">Преобразование шестнадцатеричной строки в число</span><span class="sxs-lookup"><span data-stu-id="678dd-104">To convert a hexadecimal string to a number</span></span>

- <span data-ttu-id="678dd-105">Используйте метод <xref:System.Convert.ToInt32(System.String,System.Int32)> для преобразования числа, выраженного в кодировке base-16, в целое число.</span><span class="sxs-lookup"><span data-stu-id="678dd-105">Use the <xref:System.Convert.ToInt32(System.String,System.Int32)> method to convert the number expressed in base-16 to an integer.</span></span>

  <span data-ttu-id="678dd-106">Первым аргументом метода <xref:System.Convert.ToInt32(System.String,System.Int32)> является Преобразуемая строка.</span><span class="sxs-lookup"><span data-stu-id="678dd-106">The first argument of the <xref:System.Convert.ToInt32(System.String,System.Int32)> method is the string to convert.</span></span> <span data-ttu-id="678dd-107">Второй аргумент описывает, в какой базе чисел выражается число. шестнадцатеричное число — основание 16.</span><span class="sxs-lookup"><span data-stu-id="678dd-107">The second argument describes what base the number is expressed in; hexadecimal is base 16.</span></span>

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- <span data-ttu-id="678dd-108">Обратите внимание, что шестнадцатеричная строка имеет следующие ограничения.</span><span class="sxs-lookup"><span data-stu-id="678dd-108">Note that the hexadecimal string has the following restrictions:</span></span>

  - <span data-ttu-id="678dd-109">Он не может включать префикс `&h`.</span><span class="sxs-lookup"><span data-stu-id="678dd-109">It cannot include the `&h` prefix.</span></span>
  - <span data-ttu-id="678dd-110">Он не может включать `_` разделитель цифр.</span><span class="sxs-lookup"><span data-stu-id="678dd-110">It cannot include the `_` digit separator.</span></span>

  <span data-ttu-id="678dd-111">При наличии префикса или разделителя цифр вызов метода <xref:System.Convert.ToInt32(System.String,System.Int32)> создает <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="678dd-111">If the prefix or a digit separator is present, the call to the <xref:System.Convert.ToInt32(System.String,System.Int32)> method throws a <xref:System.FormatException>.</span></span>

## <a name="see-also"></a><span data-ttu-id="678dd-112">См. также</span><span class="sxs-lookup"><span data-stu-id="678dd-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
