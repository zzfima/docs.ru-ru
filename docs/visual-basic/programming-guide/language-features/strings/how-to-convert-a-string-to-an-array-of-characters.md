---
title: Практическое руководство. Преобразование строки в массив символов
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: d2f7128f97e576d37216d3aa9736921f13f77004
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352447"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="44c66-102">Практическое руководство. Преобразование строки (String) в массив символов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="44c66-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="44c66-103">Иногда бывает полезно иметь данные о символах в строке и позициях этих символов в строке, например при анализе строки.</span><span class="sxs-lookup"><span data-stu-id="44c66-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="44c66-104">В этом примере показано, как можно получить массив символов в строке, вызвав метод <xref:System.String.ToCharArray%2A> строки.</span><span class="sxs-lookup"><span data-stu-id="44c66-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44c66-105">Пример</span><span class="sxs-lookup"><span data-stu-id="44c66-105">Example</span></span>  
 <span data-ttu-id="44c66-106">В этом примере показано, как разделить строку на `Char` массив и как разбить строку на `String` массив символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="44c66-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="44c66-107">Это различие состоит в том, что текстовые символы Юникода могут состоять из двух или более `Char` символов (например, суррогатной пары или последовательности присоединяемых символов).</span><span class="sxs-lookup"><span data-stu-id="44c66-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="44c66-108">Дополнительные сведения см. в разделе <xref:System.Globalization.TextElementEnumerator> и [стандарт Unicode](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="44c66-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="44c66-109">Пример</span><span class="sxs-lookup"><span data-stu-id="44c66-109">Example</span></span>  
 <span data-ttu-id="44c66-110">Сложнее разбить строку на символы в Юникоде, но это необходимо, если требуются сведения о визуальном представлении строки.</span><span class="sxs-lookup"><span data-stu-id="44c66-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="44c66-111">В этом примере используется метод <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> для получения сведений о символах текста Юникода, составляющих строку.</span><span class="sxs-lookup"><span data-stu-id="44c66-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="44c66-112">См. также</span><span class="sxs-lookup"><span data-stu-id="44c66-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="44c66-113">Практическое руководство. Доступ к символам в строках</span><span class="sxs-lookup"><span data-stu-id="44c66-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [<span data-ttu-id="44c66-114">Преобразование между строками и другими типами данных в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="44c66-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="44c66-115">Строки</span><span class="sxs-lookup"><span data-stu-id="44c66-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
