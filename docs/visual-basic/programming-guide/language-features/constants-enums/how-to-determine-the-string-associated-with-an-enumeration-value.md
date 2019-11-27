---
title: Практическое руководство. Определение строки, связанной со значением из перечисления
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: c396a4e2ebe973f5be65c3fab5f22cdedb29be1a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351135"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="667c1-102">Практическое руководство. Определение строки, связанной со значением из перечисления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="667c1-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="667c1-103">Методы <xref:System.Enum.GetValues%2A> и <xref:System.Enum.GetNames%2A> позволяют определить строки и значения, связанные с элементами перечисления.</span><span class="sxs-lookup"><span data-stu-id="667c1-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="667c1-104">Определение строки, связанной с перечислением</span><span class="sxs-lookup"><span data-stu-id="667c1-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="667c1-105">Используйте метод <xref:System.Enum.GetNames%2A> для получения строк, связанных с элементами перечисления.</span><span class="sxs-lookup"><span data-stu-id="667c1-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="667c1-106">В этом примере объявляется перечисление `flavorEnum`, а затем используется метод <xref:System.Enum.GetNames%2A> для вывода строк, связанных с каждым элементом.</span><span class="sxs-lookup"><span data-stu-id="667c1-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="667c1-107">См. также</span><span class="sxs-lookup"><span data-stu-id="667c1-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="667c1-108">Инструкции. Объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="667c1-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="667c1-109">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="667c1-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="667c1-110">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="667c1-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="667c1-111">Пошаговое руководство. перебор перечислений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="667c1-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="667c1-112">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="667c1-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="667c1-113">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="667c1-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
