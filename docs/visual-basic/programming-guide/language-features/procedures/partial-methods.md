---
title: Разделяемые методы (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: a974a68010fe80a07e83ac31e109bbf1c2b955e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568781"
---
# <a name="partial-methods-visual-basic"></a><span data-ttu-id="985e3-102">Разделяемые методы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="985e3-102">Partial Methods (Visual Basic)</span></span>
<span data-ttu-id="985e3-103">Разделяемые методы позволяют разработчикам использовать пользовательскую логику в код.</span><span class="sxs-lookup"><span data-stu-id="985e3-103">Partial methods enable developers to insert custom logic into code.</span></span> <span data-ttu-id="985e3-104">Как правило код входит в созданном конструктором класса.</span><span class="sxs-lookup"><span data-stu-id="985e3-104">Typically, the code is part of a designer-generated class.</span></span> <span data-ttu-id="985e3-105">Разделяемые методы определяются в разделяемый класс, созданный генератором кода, и они часто используются для предоставления уведомления, что что-то было изменено.</span><span class="sxs-lookup"><span data-stu-id="985e3-105">Partial methods are defined in a partial class that is created by a code generator, and they are commonly used to provide notification that something has been changed.</span></span> <span data-ttu-id="985e3-106">Они позволяют разработчику указать пользовательское поведение в ответ на изменение.</span><span class="sxs-lookup"><span data-stu-id="985e3-106">They enable the developer to specify custom behavior in response to the change.</span></span>  
  
 <span data-ttu-id="985e3-107">Конструктор генератора кода определяет только сигнатуру метода и один или несколько вызовов метода.</span><span class="sxs-lookup"><span data-stu-id="985e3-107">The designer of the code generator defines only the method signature and one or more calls to the method.</span></span> <span data-ttu-id="985e3-108">Разработчики могут затем предоставить реализации метода, если они хотят настроить поведение сформированного кода.</span><span class="sxs-lookup"><span data-stu-id="985e3-108">Developers can then provide implementations for the method if they want to customize the behavior of the generated code.</span></span> <span data-ttu-id="985e3-109">При реализации не указаны, вызовы метода удаляются компилятором, что потери производительности.</span><span class="sxs-lookup"><span data-stu-id="985e3-109">When no implementation is provided, calls to the method are removed by the compiler, resulting in no additional performance overhead.</span></span>  
  
## <a name="declaration"></a><span data-ttu-id="985e3-110">Объявление</span><span class="sxs-lookup"><span data-stu-id="985e3-110">Declaration</span></span>  
 <span data-ttu-id="985e3-111">Созданный код помечает определение разделяемого метода, поместив ключевое слово `Partial` в начале строки подписи.</span><span class="sxs-lookup"><span data-stu-id="985e3-111">The generated code marks the definition of a partial method by placing the keyword `Partial` at the start of the signature line.</span></span>  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 <span data-ttu-id="985e3-112">Определение должно удовлетворять следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="985e3-112">The definition must meet the following conditions:</span></span>  
  
-   <span data-ttu-id="985e3-113">Этот метод должен быть `Sub`, а не `Function`.</span><span class="sxs-lookup"><span data-stu-id="985e3-113">The method must be a `Sub`, not a `Function`.</span></span>  
  
-   <span data-ttu-id="985e3-114">Тело метода должно быть пустым.</span><span class="sxs-lookup"><span data-stu-id="985e3-114">The body of the method must be left empty.</span></span>  
  
-   <span data-ttu-id="985e3-115">Модификатор доступа должен быть `Private`.</span><span class="sxs-lookup"><span data-stu-id="985e3-115">The access modifier must be `Private`.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="985e3-116">Реализация</span><span class="sxs-lookup"><span data-stu-id="985e3-116">Implementation</span></span>  
 <span data-ttu-id="985e3-117">Реализация состоит заполнения тела разделяемого метода.</span><span class="sxs-lookup"><span data-stu-id="985e3-117">The implementation consists primarily of filling in the body of the partial method.</span></span> <span data-ttu-id="985e3-118">Реализация обычно находится в отдельном разделяемом классе из определения и записывается разработчиком, который хочет расширить созданный код.</span><span class="sxs-lookup"><span data-stu-id="985e3-118">The implementation is typically in a separate partial class from the definition, and is written by a developer who wants to extend the generated code.</span></span>  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 <span data-ttu-id="985e3-119">Предыдущий пример точно дублирует подпись в объявлении, но возможны вариации.</span><span class="sxs-lookup"><span data-stu-id="985e3-119">The previous example duplicates the signature in the declaration exactly, but variations are possible.</span></span> <span data-ttu-id="985e3-120">В частности, другие модификаторы могут добавляться, такие как `Overloads` или `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="985e3-120">In particular, other modifiers can be added, such as `Overloads` or `Overrides`.</span></span> <span data-ttu-id="985e3-121">Только один `Overrides` модификатор может применяться.</span><span class="sxs-lookup"><span data-stu-id="985e3-121">Only one `Overrides` modifier is permitted.</span></span> <span data-ttu-id="985e3-122">Дополнительные сведения о модификаторах метода, см. в разделе [оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="985e3-122">For more information about method modifiers, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="use"></a><span data-ttu-id="985e3-123">Использовать</span><span class="sxs-lookup"><span data-stu-id="985e3-123">Use</span></span>  
 <span data-ttu-id="985e3-124">Вызовите разделяемый метод, как и любой другой `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="985e3-124">You call a partial method as you would call any other `Sub` procedure.</span></span> <span data-ttu-id="985e3-125">Если метод был реализован, вычисляются аргументы и выполняется тело метода.</span><span class="sxs-lookup"><span data-stu-id="985e3-125">If the method has been implemented, the arguments are evaluated and the body of the method is executed.</span></span> <span data-ttu-id="985e3-126">Однако следует помните, что реализация разделяемого метода не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="985e3-126">However, remember that implementing a partial method is optional.</span></span> <span data-ttu-id="985e3-127">Если метод не реализован, его вызов не влияет, и выражения, которые передаются как аргументы метода не вычисляются.</span><span class="sxs-lookup"><span data-stu-id="985e3-127">If the method is not implemented, a call to it has no effect, and expressions passed as arguments to the method are not evaluated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="985e3-128">Пример</span><span class="sxs-lookup"><span data-stu-id="985e3-128">Example</span></span>  
 <span data-ttu-id="985e3-129">В файле с именем Product.Designer.vb, определить `Product` классом, имеющим `Quantity` свойство.</span><span class="sxs-lookup"><span data-stu-id="985e3-129">In a file named Product.Designer.vb, define a `Product` class that has a `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 <span data-ttu-id="985e3-130">В файле с именем Product.vb, обеспечить реализацию для `QuantityChanged`.</span><span class="sxs-lookup"><span data-stu-id="985e3-130">In a file named Product.vb, provide an implementation for `QuantityChanged`.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 <span data-ttu-id="985e3-131">Наконец, в методе Main проекта, объявите `Product` экземпляра и укажите начальное значение для его `Quantity` свойство.</span><span class="sxs-lookup"><span data-stu-id="985e3-131">Finally, in the Main method of a project, declare a `Product` instance and provide an initial value for its `Quantity` property.</span></span>  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 <span data-ttu-id="985e3-132">Откроется окно сообщения, отображается следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="985e3-132">A message box should appear that displays this message:</span></span>  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a><span data-ttu-id="985e3-133">См. также</span><span class="sxs-lookup"><span data-stu-id="985e3-133">See also</span></span>
- [<span data-ttu-id="985e3-134">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="985e3-134">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="985e3-135">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="985e3-135">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="985e3-136">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="985e3-136">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="985e3-137">Partial</span><span class="sxs-lookup"><span data-stu-id="985e3-137">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)
- [<span data-ttu-id="985e3-138">Создание кода в LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="985e3-138">Code Generation in LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="985e3-139">Добавление бизнес-логики с использованием разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="985e3-139">Adding Business Logic By Using Partial Methods</span></span>](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
