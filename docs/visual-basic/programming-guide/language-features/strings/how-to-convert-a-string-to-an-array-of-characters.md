---
title: "Практическое руководство. Преобразование строки (String) в массив символов в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59d0da52c8f78b93c76325e6242156c106deeaf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="07565-102">Практическое руководство. Преобразование строки (String) в массив символов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07565-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="07565-103">Иногда полезно располагать сведениями о символов в строке и позициях этих символов, например при анализе строки.</span><span class="sxs-lookup"><span data-stu-id="07565-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="07565-104">В этом примере показано, как получить массив символов в строку путем вызова строки <xref:System.String.ToCharArray%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="07565-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07565-105">Пример</span><span class="sxs-lookup"><span data-stu-id="07565-105">Example</span></span>  
 <span data-ttu-id="07565-106">В этом примере показано, как разбить строку в `Char` массива и как разбить строку на `String` массив знаков Юникода.</span><span class="sxs-lookup"><span data-stu-id="07565-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="07565-107">Причина различия — что Юникода может состоять из двух или более `Char` символов (например, суррогатная пара или несамостоятельных последовательность символов).</span><span class="sxs-lookup"><span data-stu-id="07565-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="07565-108">Дополнительные сведения см. в разделе <xref:System.Globalization.TextElementEnumerator> и «Стандарте Юникод» http://www.Unicode.org.</span><span class="sxs-lookup"><span data-stu-id="07565-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and "The Unicode Standard" at http://www.unicode.org.</span></span>  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="07565-109">Пример</span><span class="sxs-lookup"><span data-stu-id="07565-109">Example</span></span>  
 <span data-ttu-id="07565-110">Это более сложным для разбиения строки на знаков Юникода, но это необходимо для получения сведений о визуальном представлении строки.</span><span class="sxs-lookup"><span data-stu-id="07565-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="07565-111">В этом примере используется <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> метод, чтобы получить сведения о текстовых символов Юникода, составляющих строку.</span><span class="sxs-lookup"><span data-stu-id="07565-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="07565-112">См. также</span><span class="sxs-lookup"><span data-stu-id="07565-112">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [<span data-ttu-id="07565-113">Практическое руководство. Доступ к символам в строках</span><span class="sxs-lookup"><span data-stu-id="07565-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [<span data-ttu-id="07565-114">Преобразование между строками и другими типами данных в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07565-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="07565-115">Строки</span><span class="sxs-lookup"><span data-stu-id="07565-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
