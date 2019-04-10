---
title: Практическое руководство. Вызов процедуры свойства (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: d05c1b63f5567ade9935f80ecc022eb4840e0af0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318758"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="ad616-102">Практическое руководство. Вызов процедуры свойства (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad616-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="ad616-103">Вызов процедуры свойства хранить значение в свойстве или его значение было получено.</span><span class="sxs-lookup"><span data-stu-id="ad616-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="ad616-104">Доступ к свойству так же, можно получить доступ к переменной.</span><span class="sxs-lookup"><span data-stu-id="ad616-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="ad616-105">Свойства `Set` процедура сохраняет значение и его `Get` процедура получает значение.</span><span class="sxs-lookup"><span data-stu-id="ad616-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="ad616-106">Тем не менее не вызывается явным образом эти процедуры по имени.</span><span class="sxs-lookup"><span data-stu-id="ad616-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="ad616-107">Свойство в операторе присваивания или выражение, так же, как хранить или получить значение переменной.</span><span class="sxs-lookup"><span data-stu-id="ad616-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="ad616-108">Visual Basic выполняет вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="ad616-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="ad616-109">Чтобы вызвать процедуру свойства Get</span><span class="sxs-lookup"><span data-stu-id="ad616-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="ad616-110">Используйте имя свойства в выражении так же, используется имя переменной.</span><span class="sxs-lookup"><span data-stu-id="ad616-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="ad616-111">Свойство можно использовать везде, где можно использовать переменную или константу.</span><span class="sxs-lookup"><span data-stu-id="ad616-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="ad616-112">-или-</span><span class="sxs-lookup"><span data-stu-id="ad616-112">-or-</span></span>  
  
     <span data-ttu-id="ad616-113">Используйте имя свойства после равенства (`=`) войдите в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="ad616-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="ad616-114">В следующем примере считывается значение <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> свойство, неявно вызова его `Get` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ad616-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="ad616-115">Если свойство принимает аргументы, после имени свойства круглые скобки, чтобы заключить список аргументов.</span><span class="sxs-lookup"><span data-stu-id="ad616-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="ad616-116">Если аргументы не используются, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="ad616-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="ad616-117">Поместите аргументы в списке аргументов в скобки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="ad616-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="ad616-118">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ad616-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="ad616-119">Значение свойства входит в выражение так же, как переменная или константа, или он хранится в переменной или свойству в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="ad616-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="ad616-120">Чтобы вызвать свойство процедуры Set</span><span class="sxs-lookup"><span data-stu-id="ad616-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="ad616-121">Используйте имя свойства в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="ad616-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="ad616-122">В следующем примере значение <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> свойство, неявно вызова `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="ad616-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="ad616-123">Если свойство принимает аргументы, после имени свойства круглые скобки, чтобы заключить список аргументов.</span><span class="sxs-lookup"><span data-stu-id="ad616-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="ad616-124">Если аргументы не используются, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="ad616-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="ad616-125">Поместите аргументы в списке аргументов в скобки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="ad616-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="ad616-126">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ad616-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="ad616-127">Значение, созданное в правой части оператора присваивания хранится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="ad616-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad616-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ad616-128">See also</span></span>

- [<span data-ttu-id="ad616-129">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="ad616-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="ad616-130">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="ad616-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ad616-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="ad616-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="ad616-132">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad616-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="ad616-133">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="ad616-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="ad616-134">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="ad616-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="ad616-135">Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad616-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="ad616-136">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="ad616-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="ad616-137">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="ad616-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="ad616-138">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="ad616-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="ad616-139">Оператор Set</span><span class="sxs-lookup"><span data-stu-id="ad616-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
