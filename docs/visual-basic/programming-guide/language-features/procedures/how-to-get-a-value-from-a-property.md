---
title: "Практическое руководство. Получение значения из свойства (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cde5408ea09398a79a3da01ae9b2d0202c58eaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="f1d5e-102">Практическое руководство. Получение значения из свойства (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1d5e-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="f1d5e-103">Получить значение свойства, включая имя свойства в выражении.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="f1d5e-104">Свойство `Get` процедура получает значение, но вы не вызывается явно.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="f1d5e-105">Свойство так же, как переменную.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f1d5e-106">делает вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="f1d5e-107">Для извлечения значения из свойства</span><span class="sxs-lookup"><span data-stu-id="f1d5e-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="f1d5e-108">Используйте имя свойства в выражении так же, как имя переменной.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="f1d5e-109">Можно использовать свойство везде, где можно использовать переменную или константу.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="f1d5e-110">-или-</span><span class="sxs-lookup"><span data-stu-id="f1d5e-110">-or-</span></span>  
  
     <span data-ttu-id="f1d5e-111">Используйте имя свойства после равенства (`=`) войти в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="f1d5e-112">В следующем примере считывается значение [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `Now` свойства, неявно вызывая его `Get` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-112">The following example reads the value of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  <span data-ttu-id="f1d5e-113">Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="f1d5e-114">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="f1d5e-115">Поместите аргументы в списке аргументов в скобки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="f1d5e-116">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="f1d5e-117">Значение свойства входит в выражение так же, как переменная или константа или он хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="f1d5e-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d5e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f1d5e-118">See Also</span></span>  
 [<span data-ttu-id="f1d5e-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="f1d5e-119">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="f1d5e-120">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="f1d5e-120">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="f1d5e-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="f1d5e-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="f1d5e-122">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="f1d5e-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="f1d5e-123">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1d5e-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="f1d5e-124">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="f1d5e-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="f1d5e-125">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="f1d5e-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="f1d5e-126">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="f1d5e-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="f1d5e-127">Как: объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f1d5e-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="f1d5e-128">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="f1d5e-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
