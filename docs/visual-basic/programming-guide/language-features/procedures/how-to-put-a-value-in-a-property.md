---
title: "Практическое руководство: поместить значение в свойстве (Visual Basic) | Документы Microsoft"
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
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
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
ms.openlocfilehash: c838141a27c30b11765d30ae8b0c19bccc929f4b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="1f184-102">Практическое руководство. Запись значения в свойство (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f184-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="1f184-103">Сохраните значение в свойстве, помещая имя свойства слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="1f184-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="1f184-104">Свойство `Set` процедура сохраняет значение, но вы не вызывается явно.</span><span class="sxs-lookup"><span data-stu-id="1f184-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="1f184-105">Свойство так же, как переменную.</span><span class="sxs-lookup"><span data-stu-id="1f184-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="1f184-106">делает вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="1f184-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="1f184-107">Для хранения значений в свойстве</span><span class="sxs-lookup"><span data-stu-id="1f184-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="1f184-108">Используйте имя свойства слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="1f184-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="1f184-109">В следующем примере задается значение [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` свойство полдень, неявно вызывая его `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="1f184-109">The following example sets the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     <span data-ttu-id="1f184-110">[!code-vb[VbVbcnProcedures&11;](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1f184-110">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="1f184-111">Если свойство принимает аргументы, за именем свойства в круглые скобки, чтобы заключить список аргументов.</span><span class="sxs-lookup"><span data-stu-id="1f184-111">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1f184-112">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="1f184-112">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="1f184-113">Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="1f184-113">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1f184-114">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="1f184-114">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="1f184-115">Значение, созданное в правой части оператора присваивания, хранится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="1f184-115">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f184-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1f184-116">See Also</span></span>  
 <span data-ttu-id="1f184-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="1f184-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span></span>   
<span data-ttu-id="1f184-118"> [Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1f184-118"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="1f184-119"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="1f184-119"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="1f184-120"> [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1f184-120"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="1f184-121"> [Различия между свойствами и переменными в Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="1f184-121"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="1f184-122"> [Практическое руководство: создание свойства](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="1f184-122"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="1f184-123"> [Практическое руководство: объявление свойства со смешанным уровнем доступа](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="1f184-123"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="1f184-124"> [Практическое руководство: вызов процедуры свойства](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="1f184-124"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="1f184-125"> [Практическое руководство: объявление и вызов свойства по умолчанию в Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="1f184-125"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="1f184-126"> [Практическое руководство. Получение значения из свойства](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="1f184-126"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
