---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 9ee2c6eb123907a9e25092224a1f45578717a8c7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977153"
---
# <a name="static-visual-basic"></a><span data-ttu-id="52ec6-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ec6-102">Static (Visual Basic)</span></span>
<span data-ttu-id="52ec6-103">Указывает, что один или несколько объявленных локальных переменных по-прежнему существует и сохранять свои последние значения после завершения процедуры, в котором они объявлены.</span><span class="sxs-lookup"><span data-stu-id="52ec6-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52ec6-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="52ec6-104">Remarks</span></span>  
 <span data-ttu-id="52ec6-105">Как правило локальную переменную в процедуре перестает существовать как только выполнение процедуры прерывается.</span><span class="sxs-lookup"><span data-stu-id="52ec6-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="52ec6-106">Статическая переменная продолжает существовать и сохраняет его самое последнее значение.</span><span class="sxs-lookup"><span data-stu-id="52ec6-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="52ec6-107">В следующий раз, код вызывает процедуру, переменная не инициализируется, и она содержит последнее значение, которое было назначено его.</span><span class="sxs-lookup"><span data-stu-id="52ec6-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="52ec6-108">Статическая переменная продолжает существовать в течение времени существования класс или модуль, который определен в.</span><span class="sxs-lookup"><span data-stu-id="52ec6-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="52ec6-109">Правила</span><span class="sxs-lookup"><span data-stu-id="52ec6-109">Rules</span></span>  
  
-   <span data-ttu-id="52ec6-110">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="52ec6-110">**Declaration Context.**</span></span> <span data-ttu-id="52ec6-111">Можно использовать `Static` только на локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="52ec6-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="52ec6-112">Это означает, что контекст объявления для `Static` переменной должен быть процедурой или блок в процедуре, и не может быть исходным файлом, пространства имен, класса, структуры или модуля.</span><span class="sxs-lookup"><span data-stu-id="52ec6-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="52ec6-113">Нельзя использовать `Static` внутри структуры процедуры.</span><span class="sxs-lookup"><span data-stu-id="52ec6-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
-   <span data-ttu-id="52ec6-114">Типы данных `Static` локальные переменные не могут быть получены.</span><span class="sxs-lookup"><span data-stu-id="52ec6-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="52ec6-115">Дополнительные сведения см. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="52ec6-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
-   <span data-ttu-id="52ec6-116">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="52ec6-116">**Combined Modifiers.**</span></span> <span data-ttu-id="52ec6-117">Нельзя указать `Static` вместе с `ReadOnly`, `Shadows`, или `Shared` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="52ec6-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="52ec6-118">Поведение</span><span class="sxs-lookup"><span data-stu-id="52ec6-118">Behavior</span></span>  
 <span data-ttu-id="52ec6-119">При объявлении статической переменной в `Shared` процедура, только одна копия статическая переменная доступна для всего приложения.</span><span class="sxs-lookup"><span data-stu-id="52ec6-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="52ec6-120">Вы вызываете `Shared` имя процедуры с помощью класса, не переменную, которая указывает на экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="52ec6-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="52ec6-121">При объявлении статической переменной в процедуре, которая не `Shared`, только одна копия переменной доступен для каждого экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="52ec6-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="52ec6-122">Вызов процедуры без общего доступа, используя переменную, указывающую к определенному экземпляру класса.</span><span class="sxs-lookup"><span data-stu-id="52ec6-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52ec6-123">Пример</span><span class="sxs-lookup"><span data-stu-id="52ec6-123">Example</span></span>  
 <span data-ttu-id="52ec6-124">В следующем примере показано использование функции `Static`.</span><span class="sxs-lookup"><span data-stu-id="52ec6-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="52ec6-125">`Static` Переменной `totalSales` присваивается значение 0 только один раз.</span><span class="sxs-lookup"><span data-stu-id="52ec6-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="52ec6-126">При каждом вводе `updateSales`, `totalSales` по-прежнему имеет самое последнее значение, вычисленное для нее.</span><span class="sxs-lookup"><span data-stu-id="52ec6-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="52ec6-127">`Static` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="52ec6-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="52ec6-128">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="52ec6-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="52ec6-129">См. также</span><span class="sxs-lookup"><span data-stu-id="52ec6-129">See also</span></span>
- [<span data-ttu-id="52ec6-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="52ec6-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="52ec6-131">Общие</span><span class="sxs-lookup"><span data-stu-id="52ec6-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="52ec6-132">Время существования в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52ec6-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="52ec6-133">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="52ec6-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="52ec6-134">Структуры</span><span class="sxs-lookup"><span data-stu-id="52ec6-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="52ec6-135">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="52ec6-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="52ec6-136">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="52ec6-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
