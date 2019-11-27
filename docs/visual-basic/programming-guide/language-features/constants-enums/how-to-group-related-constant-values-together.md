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
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="fbade-102">Практическое руководство. Группирование значений связанных констант (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbade-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="fbade-103">Перечисление — это лучший способ сгруппировать связанные константы.</span><span class="sxs-lookup"><span data-stu-id="fbade-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="fbade-104">Перечисление создается с помощью оператора `Enum` в разделе Declarations класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="fbade-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="fbade-105">Дополнительные сведения см. [в разделе инструкции. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="fbade-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="fbade-106">Группирование связанных значений констант</span><span class="sxs-lookup"><span data-stu-id="fbade-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="fbade-107">Напишите объявление, которое включает уровень доступа к коду, ключевое слово `Enum` и допустимое имя.</span><span class="sxs-lookup"><span data-stu-id="fbade-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="fbade-108">В этом примере создается перечисление `Private`, `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="fbade-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="fbade-109">Определите константы в перечислении.</span><span class="sxs-lookup"><span data-stu-id="fbade-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="fbade-110">В этом примере создается перечисление `Public` `temperatureValues` и присваиваются его значения.</span><span class="sxs-lookup"><span data-stu-id="fbade-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fbade-111">См. также</span><span class="sxs-lookup"><span data-stu-id="fbade-111">See also</span></span>

- [<span data-ttu-id="fbade-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="fbade-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="fbade-113">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="fbade-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="fbade-114">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="fbade-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="fbade-115">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="fbade-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="fbade-116">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="fbade-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="fbade-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="fbade-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
