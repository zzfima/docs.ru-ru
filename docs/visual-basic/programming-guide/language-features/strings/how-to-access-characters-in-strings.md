---
title: Практическое руководство. Доступа к символам строк в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 840a769b0bb322ef7b878a312437c5ec200ab074
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054033"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="f3ed9-102">Практическое руководство. Доступа к символам строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3ed9-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="f3ed9-103">В этом примере демонстрируется использование <xref:System.String.Chars%2A> свойство для доступа к знаку в указанном расположении в строке.</span><span class="sxs-lookup"><span data-stu-id="f3ed9-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3ed9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f3ed9-104">Example</span></span>  
 <span data-ttu-id="f3ed9-105">Иногда бывает удобно иметь данные о символов в строки и позиции этих символов.</span><span class="sxs-lookup"><span data-stu-id="f3ed9-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="f3ed9-106">Можно считать строки массив символов (`Char` экземпляров); можно получить определенный символ, ссылаясь на индекс символа с помощью <xref:System.String.Chars%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f3ed9-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="f3ed9-107">`index` Параметр <xref:System.String.Chars%2A> свойство отсчитывается от нуля.</span><span class="sxs-lookup"><span data-stu-id="f3ed9-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f3ed9-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f3ed9-108">Robust Programming</span></span>  
 <span data-ttu-id="f3ed9-109"><xref:System.String.Chars%2A> Свойство возвращает символ в указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="f3ed9-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="f3ed9-110">Тем не менее некоторые символы Юникода могут быть представлены более одного символа.</span><span class="sxs-lookup"><span data-stu-id="f3ed9-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="f3ed9-111">Дополнительные сведения о том, как работать с символами Юникода, см. в разделе [как: Преобразует строку в массив символов](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="f3ed9-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="f3ed9-112"><xref:System.String.Chars%2A> Свойство выдает исключение <xref:System.IndexOutOfRangeException> исключения Если `index` параметр больше или равен длине строки, или если он меньше нуля</span><span class="sxs-lookup"><span data-stu-id="f3ed9-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ed9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f3ed9-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="f3ed9-114">Практическое руководство. Преобразует строку в массив символов</span><span class="sxs-lookup"><span data-stu-id="f3ed9-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="f3ed9-115">Преобразование между строками и другими типами данных в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3ed9-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="f3ed9-116">Строки</span><span class="sxs-lookup"><span data-stu-id="f3ed9-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
