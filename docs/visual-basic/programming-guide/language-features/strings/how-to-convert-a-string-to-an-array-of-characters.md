---
title: Практическое руководство. Преобразует строку в массив символов в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: 921d7ad62545d3a29870aee6c6b354fdadeb0500
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823315"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="bb4af-102">Практическое руководство. Преобразует строку в массив символов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb4af-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="bb4af-103">Иногда бывает удобно иметь данные о символов в строки и позиции этих символов, например при анализе строки.</span><span class="sxs-lookup"><span data-stu-id="bb4af-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="bb4af-104">В этом примере показано, как можно получить массив символов в строку путем вызова строки <xref:System.String.ToCharArray%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="bb4af-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb4af-105">Пример</span><span class="sxs-lookup"><span data-stu-id="bb4af-105">Example</span></span>  
 <span data-ttu-id="bb4af-106">В этом примере показано, как разбить строку в `Char` массива и как разбить строку на `String` массив знаков Юникода.</span><span class="sxs-lookup"><span data-stu-id="bb4af-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="bb4af-107">Это различие связано что Юникода может состоять из двух или более `Char` символов (например, суррогатная пара или несамостоятельных последовательность символов).</span><span class="sxs-lookup"><span data-stu-id="bb4af-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="bb4af-108">Дополнительные сведения см. в разделе <xref:System.Globalization.TextElementEnumerator> и [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="bb4af-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="bb4af-109">Пример</span><span class="sxs-lookup"><span data-stu-id="bb4af-109">Example</span></span>  
 <span data-ttu-id="bb4af-110">Сложнее для разбиения строки на знаков Юникода, но это необходимо, если вам нужна информация об визуальное представление строки.</span><span class="sxs-lookup"><span data-stu-id="bb4af-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="bb4af-111">В этом примере используется <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> метод для получения сведений о текстовых символов Юникода, составляющих строку.</span><span class="sxs-lookup"><span data-stu-id="bb4af-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="bb4af-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bb4af-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="bb4af-113">Практическое руководство. Доступа к символам в строках</span><span class="sxs-lookup"><span data-stu-id="bb4af-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [<span data-ttu-id="bb4af-114">Преобразование между строками и другими типами данных в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb4af-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="bb4af-115">Строки</span><span class="sxs-lookup"><span data-stu-id="bb4af-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
