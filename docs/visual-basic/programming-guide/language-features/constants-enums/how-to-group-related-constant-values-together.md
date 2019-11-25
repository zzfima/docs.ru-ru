---
title: Практическое руководство. Группирование значений связанных констант
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 151eefee4f69e1db8ba40f91334da8a051b95732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354034"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="19987-102">Практическое руководство. Группирование значений связанных констант (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19987-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="19987-103">An enumeration is the best way to group related constants together.</span><span class="sxs-lookup"><span data-stu-id="19987-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="19987-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span><span class="sxs-lookup"><span data-stu-id="19987-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="19987-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="19987-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="19987-106">To group related constant values</span><span class="sxs-lookup"><span data-stu-id="19987-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="19987-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span><span class="sxs-lookup"><span data-stu-id="19987-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="19987-108">This example creates the `Private` enumeration, `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="19987-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="19987-109">Define the constants in the enumeration.</span><span class="sxs-lookup"><span data-stu-id="19987-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="19987-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span><span class="sxs-lookup"><span data-stu-id="19987-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="19987-111">См. также</span><span class="sxs-lookup"><span data-stu-id="19987-111">See also</span></span>

- [<span data-ttu-id="19987-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="19987-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="19987-113">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="19987-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="19987-114">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="19987-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="19987-115">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="19987-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="19987-116">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="19987-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="19987-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="19987-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
