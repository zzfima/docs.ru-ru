---
title: Практическое руководство. Запись значения в свойство (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: 29e68ca2b9436921c81346eb1def2417157aae9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="982ff-102">Практическое руководство. Запись значения в свойство (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="982ff-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="982ff-103">Для сохранения значения в свойство, помещая имя свойства слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="982ff-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="982ff-104">Свойство `Set` процедура сохраняет значение, но вы не вызывается явно.</span><span class="sxs-lookup"><span data-stu-id="982ff-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="982ff-105">Свойство так же, как переменную.</span><span class="sxs-lookup"><span data-stu-id="982ff-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="982ff-106">Visual Basic выполняет вызовы процедур свойств.</span><span class="sxs-lookup"><span data-stu-id="982ff-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="982ff-107">Для хранения значений в свойстве</span><span class="sxs-lookup"><span data-stu-id="982ff-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="982ff-108">Используйте имя свойства слева от оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="982ff-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="982ff-109">В следующем примере задается значение Visual Basic `TimeOfDay` свойство полдень, неявно вызывая его `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="982ff-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]  
  
2.  <span data-ttu-id="982ff-110">Если свойство принимает аргументы, за именем свойства с помощью скобок, заключите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="982ff-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="982ff-111">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="982ff-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="982ff-112">Поместите аргументы в списке аргументов в скобки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="982ff-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="982ff-113">Убедитесь, что аргументы указаны в том же порядке, в котором свойство определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="982ff-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="982ff-114">Значение, созданное в правой части оператора присваивания, хранится в свойстве.</span><span class="sxs-lookup"><span data-stu-id="982ff-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="982ff-115">См. также</span><span class="sxs-lookup"><span data-stu-id="982ff-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>  
 [<span data-ttu-id="982ff-116">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="982ff-116">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="982ff-117">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="982ff-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="982ff-118">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="982ff-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="982ff-119">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="982ff-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="982ff-120">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="982ff-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="982ff-121">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="982ff-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="982ff-122">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="982ff-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="982ff-123">Как: объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="982ff-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="982ff-124">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="982ff-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
