---
title: "Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90fe20303f6f2ed692e54e44ee8cc65897531543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="45768-102">Практическое руководство. Объявление свойства со смешанным уровнем доступа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45768-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="45768-103">Если вы хотите `Get` и `Set` процедуры свойства для имеют разные уровни доступа, можно использовать менее строгий уровень в `Property` инструкции и более строгий уровень в любом `Get` или `Set` инструкция.</span><span class="sxs-lookup"><span data-stu-id="45768-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="45768-104">Смешанные уровни доступа используются в свойстве, когда некоторые части кода, чтобы иметь возможность получить значение свойства, а другие части кода, чтобы иметь возможность изменить значение.</span><span class="sxs-lookup"><span data-stu-id="45768-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="45768-105">Дополнительные сведения об уровнях доступа см. в разделе [уровни в Visual Basic доступа](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="45768-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="45768-106">Для объявления свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="45768-106">To declare a property with mixed access levels</span></span>  
  
1.  <span data-ttu-id="45768-107">Объявите свойство обычным способом и укажите менее строгий уровень доступа (такие как `Public`) в `Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="45768-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2.  <span data-ttu-id="45768-108">Объявление любого `Get` или `Set` процедуру, указав более строгий уровень доступа (такие как `Friend`).</span><span class="sxs-lookup"><span data-stu-id="45768-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3.  <span data-ttu-id="45768-109">Не указывайте уровень доступа для процедуры свойства.</span><span class="sxs-lookup"><span data-stu-id="45768-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="45768-110">Предполагается, что уровень доступа, объявленные в `Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="45768-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="45768-111">Можно ограничить доступ только на одном из процедур свойства.</span><span class="sxs-lookup"><span data-stu-id="45768-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](./codesnippet/VisualBasic/how-to-declare-a-property-with-mixed-access-levels_1.vb)]  
  
     <span data-ttu-id="45768-112">В приведенном выше примере `Get` процедуры имеет те же `Protected` доступ как к самому свойству, пока `Set` процедура имеет `Private` доступа.</span><span class="sxs-lookup"><span data-stu-id="45768-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="45768-113">Класс, производный от `employee` можно прочитать `salary` значение, но только `employee` класс может установить его.</span><span class="sxs-lookup"><span data-stu-id="45768-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45768-114">См. также</span><span class="sxs-lookup"><span data-stu-id="45768-114">See Also</span></span>  
 [<span data-ttu-id="45768-115">Процедуры</span><span class="sxs-lookup"><span data-stu-id="45768-115">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="45768-116">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="45768-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="45768-117">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="45768-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="45768-118">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="45768-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="45768-119">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45768-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="45768-120">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="45768-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="45768-121">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="45768-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="45768-122">Как: объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45768-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="45768-123">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="45768-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="45768-124">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="45768-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
