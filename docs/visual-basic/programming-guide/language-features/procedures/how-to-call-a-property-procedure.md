---
title: "Практическое руководство. Вызов процедуры свойства (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf9080e3c2b23302257499f13e734231f3614495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="f3d06-102">Практическое руководство. Вызов процедуры свойства (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3d06-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="f3d06-103">Вызов процедуры свойства хранения значения свойства или извлечения его значения.</span><span class="sxs-lookup"><span data-stu-id="f3d06-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="f3d06-104">Доступ к свойству так же, как можно получить доступ к переменной.</span><span class="sxs-lookup"><span data-stu-id="f3d06-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="f3d06-105">Свойство `Set` процедура сохраняет значение и его `Get` процедура получает значение.</span><span class="sxs-lookup"><span data-stu-id="f3d06-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="f3d06-106">Тем не менее не вызывается явным образом эти процедуры по имени.</span><span class="sxs-lookup"><span data-stu-id="f3d06-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="f3d06-107">Свойство в операторе присваивания или выражении так же, как и при сохранении или получить значение переменной.</span><span class="sxs-lookup"><span data-stu-id="f3d06-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f3d06-108">делает вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="f3d06-108"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="f3d06-109">Вызов процедуры свойства Get</span><span class="sxs-lookup"><span data-stu-id="f3d06-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="f3d06-110">Используйте имя свойства в выражении так же, как имя переменной.</span><span class="sxs-lookup"><span data-stu-id="f3d06-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="f3d06-111">Можно использовать свойство везде, где можно использовать переменную или константу.</span><span class="sxs-lookup"><span data-stu-id="f3d06-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="f3d06-112">-или-</span><span class="sxs-lookup"><span data-stu-id="f3d06-112">-or-</span></span>  
  
     <span data-ttu-id="f3d06-113">Используйте имя свойства после равенства (`=`) войти в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="f3d06-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="f3d06-114">В следующем примере считывается значение <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> свойства, неявно вызывая его `Get` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f3d06-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  <span data-ttu-id="f3d06-115">Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="f3d06-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="f3d06-116">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="f3d06-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="f3d06-117">Поместите аргументы в списке аргументов в скобки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="f3d06-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="f3d06-118">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f3d06-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="f3d06-119">Значение свойства входит в выражение так же, как переменная или константа или он хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="f3d06-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="f3d06-120">Для вызова свойства процедуры Set</span><span class="sxs-lookup"><span data-stu-id="f3d06-120">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="f3d06-121">Используйте имя свойства слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="f3d06-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="f3d06-122">В следующем примере задается значение <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> свойства, неявно вызова `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f3d06-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  <span data-ttu-id="f3d06-123">Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="f3d06-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="f3d06-124">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="f3d06-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="f3d06-125">Поместите аргументы в списке аргументов в скобки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="f3d06-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="f3d06-126">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f3d06-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="f3d06-127">Значение, созданное в правой части оператора присваивания, хранится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="f3d06-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d06-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f3d06-128">See Also</span></span>  
 [<span data-ttu-id="f3d06-129">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="f3d06-129">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="f3d06-130">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="f3d06-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="f3d06-131">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="f3d06-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="f3d06-132">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3d06-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="f3d06-133">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="f3d06-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="f3d06-134">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="f3d06-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="f3d06-135">Как: объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3d06-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="f3d06-136">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="f3d06-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="f3d06-137">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="f3d06-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)  
 [<span data-ttu-id="f3d06-138">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="f3d06-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="f3d06-139">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="f3d06-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
