---
title: Практическое руководство. Объявление свойства со смешанным уровнем доступа
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: d74e23f33fbf7d9d29ab84b9b1bd4fc08863ac48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349699"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="efdc1-102">Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efdc1-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="efdc1-103">Если требуется, чтобы процедуры `Get` и `Set` для свойства имели разные уровни доступа, можно использовать более строгий уровень в инструкции `Property` и более строгий уровень в инструкции `Get` или `Set`.</span><span class="sxs-lookup"><span data-stu-id="efdc1-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="efdc1-104">Смешанные уровни доступа для свойства используются, если требуется, чтобы определенные части кода могли получить значение свойства, а некоторые другие части кода могут изменить значение.</span><span class="sxs-lookup"><span data-stu-id="efdc1-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="efdc1-105">Дополнительные сведения об уровнях доступа см. [в разделе уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="efdc1-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="efdc1-106">Объявление свойства со смешанными уровнями доступа</span><span class="sxs-lookup"><span data-stu-id="efdc1-106">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="efdc1-107">Объявите свойство обычным способом и укажите менее четкий уровень доступа (например, `Public`) в инструкции `Property`.</span><span class="sxs-lookup"><span data-stu-id="efdc1-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="efdc1-108">Объявите `Get` или `Set` процедуру, указав более четкий уровень доступа (например, `Friend`).</span><span class="sxs-lookup"><span data-stu-id="efdc1-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="efdc1-109">Не указывайте уровень доступа для другой процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="efdc1-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="efdc1-110">Предполагается уровень доступа, объявленный в операторе `Property`.</span><span class="sxs-lookup"><span data-stu-id="efdc1-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="efdc1-111">Доступ можно ограничить только для одной из процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="efdc1-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="efdc1-112">В предыдущем примере процедура `Get` имеет тот же `Protected` доступ, что и само свойство, а процедура `Set` имеет `Private` доступ.</span><span class="sxs-lookup"><span data-stu-id="efdc1-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="efdc1-113">Класс, производный от `employee`, может считывать `salary` значение, но только класс `employee` может его задать.</span><span class="sxs-lookup"><span data-stu-id="efdc1-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdc1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="efdc1-114">See also</span></span>

- [<span data-ttu-id="efdc1-115">Процедуры</span><span class="sxs-lookup"><span data-stu-id="efdc1-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="efdc1-116">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="efdc1-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="efdc1-117">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="efdc1-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="efdc1-118">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="efdc1-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="efdc1-119">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efdc1-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="efdc1-120">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="efdc1-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="efdc1-121">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="efdc1-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="efdc1-122">Инструкции. объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efdc1-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="efdc1-123">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="efdc1-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="efdc1-124">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="efdc1-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
