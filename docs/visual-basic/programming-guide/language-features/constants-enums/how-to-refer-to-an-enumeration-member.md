---
title: Практическое руководство. Ссылка на член перечисления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: e9ea359d58dfa11f7bba7fec3d31955e18d24953
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813981"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="ddafb-102">Практическое руководство. Ссылка на член перечисления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddafb-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="ddafb-103">Перечисления предоставляют удобный способ работы с наборами связанных констант и связывать постоянные значения с именами.</span><span class="sxs-lookup"><span data-stu-id="ddafb-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="ddafb-104">Например, вы можете объявить перечисление для набора целочисленных констант, связанных с днями недели, а затем использовать в коде названия дней, а не числа.</span><span class="sxs-lookup"><span data-stu-id="ddafb-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="ddafb-105">Чтобы не использовать полные имена с `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ddafb-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="ddafb-106">Дополнительные сведения см. в разделе [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="ddafb-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="ddafb-107">Для ссылки на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="ddafb-107">To refer to an enumeration member</span></span>  
  
-   <span data-ttu-id="ddafb-108">Уточнить имя члена с помощью перечисления.</span><span class="sxs-lookup"><span data-stu-id="ddafb-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="ddafb-109">Например, в следующем примере назначается `Saturday` членом `FirstDayOfWeek` перечисления переменной `DayValue`.</span><span class="sxs-lookup"><span data-stu-id="ddafb-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="ddafb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ddafb-110">See also</span></span>

- [<span data-ttu-id="ddafb-111">Практическое руководство. Объявления перечисления</span><span class="sxs-lookup"><span data-stu-id="ddafb-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="ddafb-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="ddafb-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="ddafb-113">Практическое руководство. Перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddafb-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="ddafb-114">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="ddafb-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="ddafb-115">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="ddafb-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
