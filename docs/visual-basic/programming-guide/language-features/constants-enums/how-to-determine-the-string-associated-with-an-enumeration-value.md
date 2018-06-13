---
title: Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c14ea61feba7d7d85f9a4fc377aefdd8fa240c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651704"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="24ad6-102">Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24ad6-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="24ad6-103"><xref:System.Enum.GetValues%2A> И <xref:System.Enum.GetNames%2A> методы позволяют определить строки и значения, связанные с членами перечисления.</span><span class="sxs-lookup"><span data-stu-id="24ad6-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="24ad6-104">Чтобы определить строку, связанную с перечислением</span><span class="sxs-lookup"><span data-stu-id="24ad6-104">To determine the string associated with an enumeration</span></span>  
  
-   <span data-ttu-id="24ad6-105">Используйте <xref:System.Enum.GetNames%2A> метод для извлечения строки, связанные с членами перечисления.</span><span class="sxs-lookup"><span data-stu-id="24ad6-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="24ad6-106">В этом примере объявляется перечисление, `flavorEnum`, затем использует <xref:System.Enum.GetNames%2A> метод для отображения строк, связанных с каждым элементом.</span><span class="sxs-lookup"><span data-stu-id="24ad6-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="24ad6-107">См. также</span><span class="sxs-lookup"><span data-stu-id="24ad6-107">See Also</span></span>  
 <xref:System.Enum.GetValues%2A>  
 <xref:System.Enum.GetNames%2A>  
 <xref:System.Enum>  
 [<span data-ttu-id="24ad6-108">Как: объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="24ad6-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="24ad6-109">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="24ad6-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="24ad6-110">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="24ad6-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="24ad6-111">Как: перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24ad6-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="24ad6-112">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="24ad6-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="24ad6-113">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="24ad6-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
