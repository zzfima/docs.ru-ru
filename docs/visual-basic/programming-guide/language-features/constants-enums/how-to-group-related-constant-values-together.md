---
title: "Практическое руководство. Группирование значений связанных констант (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be57b56047654d6eb3536bb0b8f63eca27decdb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="30d1a-102">Практическое руководство. Группирование значений связанных констант (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30d1a-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="30d1a-103">Перечисление является лучшим способом группирования связанных констант.</span><span class="sxs-lookup"><span data-stu-id="30d1a-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="30d1a-104">Создать перечисление с `Enum` инструкции в разделе объявлений класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="30d1a-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="30d1a-105">Дополнительные сведения см. в разделе [как: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="30d1a-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="30d1a-106">Группу значений связанных констант</span><span class="sxs-lookup"><span data-stu-id="30d1a-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="30d1a-107">Написать объявление, которое включает уровень доступа к коду, `Enum` ключевое слово и допустимое имя.</span><span class="sxs-lookup"><span data-stu-id="30d1a-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="30d1a-108">В этом примере создается `Private` перечисления `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="30d1a-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="30d1a-109">Определения констант в перечислении.</span><span class="sxs-lookup"><span data-stu-id="30d1a-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="30d1a-110">В этом примере создается `Public` перечисления `temperatureValues` и присваивает его значения.</span><span class="sxs-lookup"><span data-stu-id="30d1a-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="30d1a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="30d1a-111">See Also</span></span>  
 [<span data-ttu-id="30d1a-112">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="30d1a-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="30d1a-113">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="30d1a-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="30d1a-114">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="30d1a-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="30d1a-115">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="30d1a-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="30d1a-116">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="30d1a-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="30d1a-117">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="30d1a-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
