---
title: "Практическое руководство. Запись значения в свойство (Visual Basic)"
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
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44e7c4a92ea3d087c12e74aa2ede33a52c8730cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="0e354-102">Практическое руководство. Запись значения в свойство (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e354-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="0e354-103">Для сохранения значения в свойство, помещая имя свойства слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="0e354-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="0e354-104">Свойство `Set` процедура сохраняет значение, но вы не вызывается явно.</span><span class="sxs-lookup"><span data-stu-id="0e354-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="0e354-105">Свойство так же, как переменную.</span><span class="sxs-lookup"><span data-stu-id="0e354-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="0e354-106">делает вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="0e354-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="0e354-107">Для хранения значений в свойстве</span><span class="sxs-lookup"><span data-stu-id="0e354-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="0e354-108">Используйте имя свойства слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="0e354-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="0e354-109">В следующем примере задается значение [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `TimeOfDay` свойство полдень, неявно вызывая его `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="0e354-109">The following example sets the value of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  <span data-ttu-id="0e354-110">Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="0e354-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="0e354-111">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="0e354-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="0e354-112">Поместите аргументы в списке аргументов в скобки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="0e354-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="0e354-113">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="0e354-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="0e354-114">Значение, созданное в правой части оператора присваивания, хранится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="0e354-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e354-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0e354-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [<span data-ttu-id="0e354-116">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="0e354-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="0e354-117">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="0e354-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="0e354-118">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="0e354-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="0e354-119">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e354-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="0e354-120">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="0e354-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="0e354-121">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="0e354-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="0e354-122">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="0e354-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="0e354-123">Как: объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e354-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="0e354-124">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="0e354-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
