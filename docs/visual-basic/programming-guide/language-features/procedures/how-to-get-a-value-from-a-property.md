---
title: "Практическое руководство: получение значения из свойства (Visual Basic) | Документы Microsoft"
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
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
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
ms.openlocfilehash: 719a4fc9ff163fb4437ea40c8265a5e36232347e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="3f22f-102">Практическое руководство. Получение значения из свойства (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f22f-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="3f22f-103">Получить значение свойства, включая имя свойства в выражении.</span><span class="sxs-lookup"><span data-stu-id="3f22f-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="3f22f-104">Свойство `Get` процедура получает значение, но вы не вызывается явно.</span><span class="sxs-lookup"><span data-stu-id="3f22f-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="3f22f-105">Свойство так же, как переменную.</span><span class="sxs-lookup"><span data-stu-id="3f22f-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="3f22f-106">делает вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="3f22f-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="3f22f-107">Для извлечения значения из свойства</span><span class="sxs-lookup"><span data-stu-id="3f22f-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="3f22f-108">Используйте имя свойства в выражении так же, как имя переменной.</span><span class="sxs-lookup"><span data-stu-id="3f22f-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="3f22f-109">Можно использовать свойство везде, где можно использовать переменную или константу.</span><span class="sxs-lookup"><span data-stu-id="3f22f-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="3f22f-110">-или-</span><span class="sxs-lookup"><span data-stu-id="3f22f-110">-or-</span></span>  
  
     <span data-ttu-id="3f22f-111">Используйте имя свойства после равенства (`=`) входа в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="3f22f-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="3f22f-112">В следующем примере считывается значение [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` свойства, неявно вызывая его `Get` процедуры.</span><span class="sxs-lookup"><span data-stu-id="3f22f-112">The following example reads the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="3f22f-113">[!code-vb[VbVbalrDateProperties&#4;](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3f22f-113">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="3f22f-114">Если свойство принимает аргументы, за именем свойства в круглые скобки, чтобы заключить список аргументов.</span><span class="sxs-lookup"><span data-stu-id="3f22f-114">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="3f22f-115">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="3f22f-115">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="3f22f-116">Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="3f22f-116">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="3f22f-117">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="3f22f-117">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="3f22f-118">Значение свойства входит в выражение так же, как переменная или константа или хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="3f22f-118">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f22f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3f22f-119">See Also</span></span>  
 <span data-ttu-id="3f22f-120">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-120">[Procedures](./index.md) </span></span>  
<span data-ttu-id="3f22f-121"> [Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="3f22f-122"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-122"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="3f22f-123"> [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-123"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="3f22f-124"> [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-124"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="3f22f-125"> [Практическое руководство: создание свойства](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-125"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="3f22f-126"> [Практическое руководство: объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-126"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="3f22f-127"> [Практическое руководство: вызов процедуры свойства](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-127"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="3f22f-128"> [Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="3f22f-128"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="3f22f-129"> [Практическое руководство. Запись значения в свойство](./how-to-put-a-value-in-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="3f22f-129"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md)</span></span>
