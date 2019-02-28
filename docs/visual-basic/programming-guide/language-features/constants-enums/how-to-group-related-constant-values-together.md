---
title: Практическое руководство. Группа связанных констант вместе (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 63475487c8a35f5b306b28d4e7097324bef00d85
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977829"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="edb25-102">Практическое руководство. Группа связанных констант вместе (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edb25-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="edb25-103">Перечисление — лучший способ группирования связанных констант.</span><span class="sxs-lookup"><span data-stu-id="edb25-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="edb25-104">Создать перечисление с `Enum` инструкцию в раздел объявлений класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="edb25-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="edb25-105">Дополнительные сведения см. в разделе [Как Объявить перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="edb25-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="edb25-106">К группе значений связанных констант</span><span class="sxs-lookup"><span data-stu-id="edb25-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="edb25-107">Написать объявление, которое включает в себя уровень доступа к коду, `Enum` ключевое слово и допустимое имя.</span><span class="sxs-lookup"><span data-stu-id="edb25-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="edb25-108">В этом примере создается `Private` перечисления, `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="edb25-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2.  <span data-ttu-id="edb25-109">Определения констант в перечислении.</span><span class="sxs-lookup"><span data-stu-id="edb25-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="edb25-110">В этом примере создается `Public` перечисления `temperatureValues` и присваивает его значения.</span><span class="sxs-lookup"><span data-stu-id="edb25-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="edb25-111">См. также</span><span class="sxs-lookup"><span data-stu-id="edb25-111">See also</span></span>
- [<span data-ttu-id="edb25-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="edb25-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="edb25-113">Практическое руководство. Ссылка на член перечисления</span><span class="sxs-lookup"><span data-stu-id="edb25-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="edb25-114">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="edb25-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="edb25-115">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="edb25-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="edb25-116">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="edb25-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="edb25-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="edb25-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
