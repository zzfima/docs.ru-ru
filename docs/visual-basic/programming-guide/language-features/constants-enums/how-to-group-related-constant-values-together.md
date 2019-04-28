---
title: Практическое руководство. Группа связанных констант вместе (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: a4f74e48cfdd5c0bc0f745d0f32eb39442f5bd83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906767"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="06427-102">Практическое руководство. Группа связанных констант вместе (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06427-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="06427-103">Перечисление — лучший способ группирования связанных констант.</span><span class="sxs-lookup"><span data-stu-id="06427-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="06427-104">Создать перечисление с `Enum` инструкцию в раздел объявлений класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="06427-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="06427-105">Дополнительные сведения см. в разделе [Как Объявить перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="06427-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="06427-106">К группе значений связанных констант</span><span class="sxs-lookup"><span data-stu-id="06427-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="06427-107">Написать объявление, которое включает в себя уровень доступа к коду, `Enum` ключевое слово и допустимое имя.</span><span class="sxs-lookup"><span data-stu-id="06427-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="06427-108">В этом примере создается `Private` перечисления, `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="06427-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="06427-109">Определения констант в перечислении.</span><span class="sxs-lookup"><span data-stu-id="06427-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="06427-110">В этом примере создается `Public` перечисления `temperatureValues` и присваивает его значения.</span><span class="sxs-lookup"><span data-stu-id="06427-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="06427-111">См. также</span><span class="sxs-lookup"><span data-stu-id="06427-111">See also</span></span>

- [<span data-ttu-id="06427-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="06427-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="06427-113">Практическое руководство. Ссылка на член перечисления</span><span class="sxs-lookup"><span data-stu-id="06427-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="06427-114">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="06427-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="06427-115">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="06427-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="06427-116">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="06427-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="06427-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="06427-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
