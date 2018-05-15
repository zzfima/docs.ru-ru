---
title: Практическое руководство. Преобразование массива байтов в строку в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: c22ae89322230d8a98ae3ae2c1485e73456e0a7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="ed47b-102">Практическое руководство. Преобразование массива байтов в строку в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed47b-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="ed47b-103">В этом разделе показано, как преобразовать байты из массива байтов в строку.</span><span class="sxs-lookup"><span data-stu-id="ed47b-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed47b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ed47b-104">Example</span></span>  
 <span data-ttu-id="ed47b-105">В этом примере используется <xref:System.Text.Encoding.GetString%2A> метод <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> кодирование класса для преобразования всех байтов из массива байтов в строку.</span><span class="sxs-lookup"><span data-stu-id="ed47b-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-an-array-of-bytes-into-a-string_1.vb)]  
  
 <span data-ttu-id="ed47b-106">Можно выбрать из нескольких параметров кодирования для преобразования массива байтов в строку:</span><span class="sxs-lookup"><span data-stu-id="ed47b-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
-   <span data-ttu-id="ed47b-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Возвращает кодировку для символов ASCII (7-разрядных) в наборе.</span><span class="sxs-lookup"><span data-stu-id="ed47b-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
-   <span data-ttu-id="ed47b-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-16 с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="ed47b-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
-   <span data-ttu-id="ed47b-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Возвращает кодировку для текущей кодовой страницы ANSI системы.</span><span class="sxs-lookup"><span data-stu-id="ed47b-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
-   <span data-ttu-id="ed47b-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-16 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="ed47b-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="ed47b-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-32 с прямым порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="ed47b-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="ed47b-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-7.</span><span class="sxs-lookup"><span data-stu-id="ed47b-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
-   <span data-ttu-id="ed47b-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Возвращает кодировку для формата UTF-8.</span><span class="sxs-lookup"><span data-stu-id="ed47b-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed47b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ed47b-114">See Also</span></span>  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetString%2A>  
 [<span data-ttu-id="ed47b-115">Как: преобразование строки в массив байтов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed47b-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
