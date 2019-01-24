---
title: Как выполнить Определение строки, связанной со значением из перечисления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 92d2e9918429c9cf408f288f832e4615b95ad423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690193"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="899e8-102">Как выполнить Определение строки, связанной со значением из перечисления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="899e8-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="899e8-103"><xref:System.Enum.GetValues%2A> И <xref:System.Enum.GetNames%2A> методы позволяют определить строки и значения, связанные с членами перечисления.</span><span class="sxs-lookup"><span data-stu-id="899e8-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="899e8-104">Чтобы определить строки, связанной с перечислением</span><span class="sxs-lookup"><span data-stu-id="899e8-104">To determine the string associated with an enumeration</span></span>  
  
-   <span data-ttu-id="899e8-105">Используйте <xref:System.Enum.GetNames%2A> метод для извлечения строки, связанные с членами перечисления.</span><span class="sxs-lookup"><span data-stu-id="899e8-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="899e8-106">В этом примере объявляется перечисление, `flavorEnum`, затем использует <xref:System.Enum.GetNames%2A> метод для отображения строк, связанных с каждым элементом.</span><span class="sxs-lookup"><span data-stu-id="899e8-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="899e8-107">См. также</span><span class="sxs-lookup"><span data-stu-id="899e8-107">See also</span></span>
- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="899e8-108">Практическое руководство. Объявления перечисления</span><span class="sxs-lookup"><span data-stu-id="899e8-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="899e8-109">Практическое руководство. Ссылка на член перечисления</span><span class="sxs-lookup"><span data-stu-id="899e8-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="899e8-110">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="899e8-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="899e8-111">Практическое руководство. Перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="899e8-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="899e8-112">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="899e8-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="899e8-113">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="899e8-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
