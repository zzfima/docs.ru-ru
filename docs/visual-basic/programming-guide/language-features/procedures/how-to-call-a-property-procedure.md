---
title: "Практическое руководство: вызов процедуры свойства (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], property procedures
- procedure calls, property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d0d37fc2b7ae1d563a7e9d0a8e75343dd690089b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="2a69e-102">Практическое руководство. Вызов процедуры свойства (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a69e-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="2a69e-103">Вызов процедуры свойства хранения значения свойства или извлечения его значения.</span><span class="sxs-lookup"><span data-stu-id="2a69e-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="2a69e-104">Доступ к свойству так же, можно получить доступ к переменной.</span><span class="sxs-lookup"><span data-stu-id="2a69e-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="2a69e-105">Свойство `Set` процедура сохраняет значение и его `Get` процедура получает значение.</span><span class="sxs-lookup"><span data-stu-id="2a69e-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="2a69e-106">Тем не менее не вызывается явным образом эти процедуры по имени.</span><span class="sxs-lookup"><span data-stu-id="2a69e-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="2a69e-107">Свойство в операторе присваивания или выражении так же, как хранить или извлекать значения переменной.</span><span class="sxs-lookup"><span data-stu-id="2a69e-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="2a69e-108">делает вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="2a69e-108"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="2a69e-109">Для вызова процедуры Get свойства</span><span class="sxs-lookup"><span data-stu-id="2a69e-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="2a69e-110">Используйте имя свойства в выражении так же, как имя переменной.</span><span class="sxs-lookup"><span data-stu-id="2a69e-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="2a69e-111">Можно использовать свойство везде, где можно использовать переменную или константу.</span><span class="sxs-lookup"><span data-stu-id="2a69e-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="2a69e-112">-или-</span><span class="sxs-lookup"><span data-stu-id="2a69e-112">-or-</span></span>  
  
     <span data-ttu-id="2a69e-113">Используйте имя свойства после равенства (`=`) входа в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="2a69e-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="2a69e-114">В следующем примере считывается значение <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>Свойства, неявно вызывая его `Get` процедуры.</xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="2a69e-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="2a69e-115">[!code-vb[VbVbalrDateProperties&#4;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a69e-115">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="2a69e-116">Если свойство принимает аргументы, за именем свойства в круглые скобки, чтобы заключить список аргументов.</span><span class="sxs-lookup"><span data-stu-id="2a69e-116">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="2a69e-117">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="2a69e-117">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="2a69e-118">Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="2a69e-118">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="2a69e-119">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="2a69e-119">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="2a69e-120">Значение свойства входит в выражение так же, как переменная или константа или хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="2a69e-120">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="2a69e-121">Чтобы вызвать свойство процедуры Set</span><span class="sxs-lookup"><span data-stu-id="2a69e-121">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="2a69e-122">Используйте имя свойства слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="2a69e-122">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="2a69e-123">В следующем примере задается значение <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>Свойства, неявно вызова `Set` процедуры.</xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="2a69e-123">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     <span data-ttu-id="2a69e-124">[!code-vb[VbVbcnProcedures&11;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a69e-124">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span></span>  
  
2.  <span data-ttu-id="2a69e-125">Если свойство принимает аргументы, за именем свойства в круглые скобки, чтобы заключить список аргументов.</span><span class="sxs-lookup"><span data-stu-id="2a69e-125">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="2a69e-126">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="2a69e-126">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="2a69e-127">Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="2a69e-127">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="2a69e-128">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="2a69e-128">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="2a69e-129">Значение, созданное в правой части оператора присваивания, хранится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="2a69e-129">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a69e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2a69e-130">See Also</span></span>  
 <span data-ttu-id="2a69e-131">[Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-131">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="2a69e-132"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="2a69e-133"> [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-133"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="2a69e-134"> [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-134"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="2a69e-135"> [Практическое руководство: создание свойства](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-135"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="2a69e-136"> [Практическое руководство: объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-136"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="2a69e-137"> [Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-137"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="2a69e-138"> [Практическое руководство: поместить значение в свойстве](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-138"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="2a69e-139"> [Практическое руководство: получение значения из свойства](./how-to-get-a-value-from-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-139"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md) </span></span>  
<span data-ttu-id="2a69e-140"> [Оператор Get](../../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2a69e-140"> [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="2a69e-141"> [Оператор Set](../../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="2a69e-141"> [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
