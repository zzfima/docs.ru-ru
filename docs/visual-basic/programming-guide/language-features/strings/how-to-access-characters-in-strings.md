---
title: Практическое руководство. Доступ к символам строк в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 48507cade639660e6ce36697975d09fb29206c20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649156"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="b09aa-102">Практическое руководство. Доступ к символам строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b09aa-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="b09aa-103">В этом примере демонстрируется использование <xref:System.String.Chars%2A> свойство для доступа к знаку в указанном месте в строке.</span><span class="sxs-lookup"><span data-stu-id="b09aa-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b09aa-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b09aa-104">Example</span></span>  
 <span data-ttu-id="b09aa-105">Иногда полезно располагать сведениями о знаков в строки и позиции этих символов.</span><span class="sxs-lookup"><span data-stu-id="b09aa-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="b09aa-106">Строку можно представить как массив символов (`Char` экземпляров); конкретного символа можно получить с помощью ссылки на индекс символа с помощью <xref:System.String.Chars%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b09aa-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 <span data-ttu-id="b09aa-107">`index` Параметр <xref:System.String.Chars%2A> свойства начинается с нуля.</span><span class="sxs-lookup"><span data-stu-id="b09aa-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b09aa-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="b09aa-108">Robust Programming</span></span>  
 <span data-ttu-id="b09aa-109"><xref:System.String.Chars%2A> Свойство возвращает символ в указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="b09aa-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="b09aa-110">Тем не менее некоторые символы Юникода могут представляться на более чем один символ.</span><span class="sxs-lookup"><span data-stu-id="b09aa-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="b09aa-111">Дополнительные сведения о том, как работать с символами Юникода см. в разделе [как: преобразование строкового значения в массиве символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="b09aa-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="b09aa-112"><xref:System.String.Chars%2A> Свойство выдает <xref:System.IndexOutOfRangeException> исключения Если `index` параметр больше или равным длине строки, или если он меньше нуля</span><span class="sxs-lookup"><span data-stu-id="b09aa-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09aa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b09aa-113">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 [<span data-ttu-id="b09aa-114">Практическое руководство. Преобразование строки в массив символов</span><span class="sxs-lookup"><span data-stu-id="b09aa-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [<span data-ttu-id="b09aa-115">Преобразование между строками и другими типами данных в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b09aa-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="b09aa-116">Строки</span><span class="sxs-lookup"><span data-stu-id="b09aa-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
