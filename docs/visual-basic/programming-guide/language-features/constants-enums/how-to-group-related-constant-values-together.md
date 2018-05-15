---
title: Практическое руководство. Группирование значений связанных констант (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 320373116ad4d61293690353fce6b7b152e79a4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="c940e-102">Практическое руководство. Группирование значений связанных констант (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c940e-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="c940e-103">Перечисление является лучшим способом группирования связанных констант.</span><span class="sxs-lookup"><span data-stu-id="c940e-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="c940e-104">Создать перечисление с `Enum` инструкции в разделе объявлений класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="c940e-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="c940e-105">Дополнительные сведения см. в разделе [как: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="c940e-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="c940e-106">Группу значений связанных констант</span><span class="sxs-lookup"><span data-stu-id="c940e-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="c940e-107">Написать объявление, которое включает уровень доступа к коду, `Enum` ключевое слово и допустимое имя.</span><span class="sxs-lookup"><span data-stu-id="c940e-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="c940e-108">В этом примере создается `Private` перечисления `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="c940e-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="c940e-109">Определения констант в перечислении.</span><span class="sxs-lookup"><span data-stu-id="c940e-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="c940e-110">В этом примере создается `Public` перечисления `temperatureValues` и присваивает его значения.</span><span class="sxs-lookup"><span data-stu-id="c940e-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c940e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c940e-111">See Also</span></span>  
 [<span data-ttu-id="c940e-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="c940e-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="c940e-113">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="c940e-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="c940e-114">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="c940e-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="c940e-115">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="c940e-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="c940e-116">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="c940e-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="c940e-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="c940e-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
