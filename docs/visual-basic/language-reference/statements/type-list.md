---
title: Список типов (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: d071e59d94e51ca55167983d0ee3098bd5c7dd8f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843634"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="01191-102">Список типов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01191-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="01191-103">Указывает *параметры типа* для *универсального* программный элемент.</span><span class="sxs-lookup"><span data-stu-id="01191-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="01191-104">Несколько параметров разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="01191-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="01191-105">Ниже приведен синтаксис для одного параметра типа.</span><span class="sxs-lookup"><span data-stu-id="01191-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01191-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01191-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="01191-107">Части</span><span class="sxs-lookup"><span data-stu-id="01191-107">Parts</span></span>  
  
|<span data-ttu-id="01191-108">Термин</span><span class="sxs-lookup"><span data-stu-id="01191-108">Term</span></span>|<span data-ttu-id="01191-109">Определение</span><span class="sxs-lookup"><span data-stu-id="01191-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="01191-110">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="01191-110">Optional.</span></span> <span data-ttu-id="01191-111">Можно использовать только в универсальных интерфейсах и делегатах.</span><span class="sxs-lookup"><span data-stu-id="01191-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="01191-112">Можно объявить тип ковариантным с помощью [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) ключевое слово или контравариантные с помощью [в](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="01191-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="01191-113">См. раздел [Ковариация и контрвариация](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="01191-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="01191-114">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="01191-114">Required.</span></span> <span data-ttu-id="01191-115">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="01191-115">Name of the type parameter.</span></span> <span data-ttu-id="01191-116">Это заполнитель, заменяется на определенный тип, предоставленный соответствующим аргументом типа.</span><span class="sxs-lookup"><span data-stu-id="01191-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="01191-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="01191-117">Optional.</span></span> <span data-ttu-id="01191-118">Список требований, ограничивающих тип данных, который может быть предоставлено `typename`.</span><span class="sxs-lookup"><span data-stu-id="01191-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="01191-119">Если у вас есть несколько ограничений, заключайте их в фигурные скобки (`{ }`) и разделяйте их запятыми.</span><span class="sxs-lookup"><span data-stu-id="01191-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="01191-120">Данные необходимо ввести список ограничений с [как](../../../visual-basic/language-reference/statements/as-clause.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="01191-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="01191-121">Использовании `As` только один раз, в начале списка.</span><span class="sxs-lookup"><span data-stu-id="01191-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01191-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="01191-122">Remarks</span></span>  
 <span data-ttu-id="01191-123">Каждый стандартный программный элемент необходимо выполнить хотя бы один параметр типа.</span><span class="sxs-lookup"><span data-stu-id="01191-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="01191-124">Параметр типа является заполнителем для определенного типа ( *сконструированный элемент*), в коде клиента указывается при создании экземпляра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="01191-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="01191-125">Можно определить универсальный класс, структура, интерфейс, процедуру или делегат.</span><span class="sxs-lookup"><span data-stu-id="01191-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="01191-126">Дополнительные сведения о том, когда для определения универсального типа см. в разделе [универсальных типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="01191-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="01191-127">Дополнительные сведения о имена параметров-типов, см. в разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="01191-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="01191-128">Правила</span><span class="sxs-lookup"><span data-stu-id="01191-128">Rules</span></span>  
  
-   <span data-ttu-id="01191-129">**Круглые скобки.**</span><span class="sxs-lookup"><span data-stu-id="01191-129">**Parentheses.**</span></span> <span data-ttu-id="01191-130">Если указать список параметров типа, его необходимо заключить в круглые скобки и данные необходимо ввести список с [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="01191-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="01191-131">Использовании `Of` только один раз, в начале списка.</span><span class="sxs-lookup"><span data-stu-id="01191-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="01191-132">**Ограничения.**</span><span class="sxs-lookup"><span data-stu-id="01191-132">**Constraints.**</span></span> <span data-ttu-id="01191-133">Список *ограничения* для типа параметра можно включить следующие элементы в любой комбинации:</span><span class="sxs-lookup"><span data-stu-id="01191-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="01191-134">Любое число интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="01191-134">Any number of interfaces.</span></span> <span data-ttu-id="01191-135">Указанный тип должен реализовывать каждый интерфейс в этом списке.</span><span class="sxs-lookup"><span data-stu-id="01191-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="01191-136">Не более одного класса.</span><span class="sxs-lookup"><span data-stu-id="01191-136">At most one class.</span></span> <span data-ttu-id="01191-137">Указанный тип должен наследовать от этого класса.</span><span class="sxs-lookup"><span data-stu-id="01191-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="01191-138">Ключевое слово `New`.</span><span class="sxs-lookup"><span data-stu-id="01191-138">The `New` keyword.</span></span> <span data-ttu-id="01191-139">Тип должен предоставлять конструктор без параметров, можно получить доступ к вашей универсального типа.</span><span class="sxs-lookup"><span data-stu-id="01191-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="01191-140">Это полезно в том случае, если ограничения параметра типа, один или несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="01191-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="01191-141">Тип, реализующий интерфейсы не обязательно предоставлять конструктор, и в зависимости от уровня доступа конструктора, код внутри универсального типа не может быть получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="01191-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="01191-142">Либо `Class` ключевое слово или `Structure` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="01191-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="01191-143">`Class` Ключевое слово ограничивает параметр универсального типа для требуют любой тип аргумента, переданного ему был ссылочным типом, например, строка, массив или делегат, или объект, созданный из класса.</span><span class="sxs-lookup"><span data-stu-id="01191-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="01191-144">`Structure` Ключевое слово ограничивает параметр универсального типа для требуют, что любой тип аргумента, переданного ему был типом значения, например структуры, перечисления или простым типом данных.</span><span class="sxs-lookup"><span data-stu-id="01191-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="01191-145">Нельзя включать оба `Class` и `Structure` в том же `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="01191-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="01191-146">Указанный тип должен удовлетворять каждому требованию, добавляемых в `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="01191-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="01191-147">Ограничения для каждого параметра типа не зависят от ограничений для других параметров типа.</span><span class="sxs-lookup"><span data-stu-id="01191-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="01191-148">Поведение</span><span class="sxs-lookup"><span data-stu-id="01191-148">Behavior</span></span>  
  
-   <span data-ttu-id="01191-149">**Подстановка во время компиляции.**</span><span class="sxs-lookup"><span data-stu-id="01191-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="01191-150">При создании сконструированный тип из универсального элемента программирования, вам предоставляется определенный тип для каждого параметра типа.</span><span class="sxs-lookup"><span data-stu-id="01191-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="01191-151">Компилятор Visual Basic подставляет данный предоставленный тип для каждого из вхождений `typename` в стандартном элементе.</span><span class="sxs-lookup"><span data-stu-id="01191-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="01191-152">**Отсутствие ограничений.**</span><span class="sxs-lookup"><span data-stu-id="01191-152">**Absence of Constraints.**</span></span> <span data-ttu-id="01191-153">Если вы не укажете все ограничения для параметра типа, код ограничивается операции и элементы, поддерживаемые [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) для этого параметра типа.</span><span class="sxs-lookup"><span data-stu-id="01191-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01191-154">Пример</span><span class="sxs-lookup"><span data-stu-id="01191-154">Example</span></span>  
 <span data-ttu-id="01191-155">В следующем примере показано каркасное определение класса универсального словаря dictionary, включая каркас функции для добавления новой записи в словарь.</span><span class="sxs-lookup"><span data-stu-id="01191-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="01191-156">Пример</span><span class="sxs-lookup"><span data-stu-id="01191-156">Example</span></span>  
 <span data-ttu-id="01191-157">Поскольку `dictionary` является универсальным, использующий ее код можно создать различные объекты из него, каждый необходимости те же функциональные возможности, но выполняется на другой тип данных.</span><span class="sxs-lookup"><span data-stu-id="01191-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="01191-158">В следующем примере показано строку кода, который создает `dictionary` со `String` записей и `Integer` ключи.</span><span class="sxs-lookup"><span data-stu-id="01191-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="01191-159">Пример</span><span class="sxs-lookup"><span data-stu-id="01191-159">Example</span></span>  
 <span data-ttu-id="01191-160">В следующем примере каркас определения, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="01191-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="01191-161">См. также</span><span class="sxs-lookup"><span data-stu-id="01191-161">See also</span></span>

- [<span data-ttu-id="01191-162">Of</span><span class="sxs-lookup"><span data-stu-id="01191-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="01191-163">Оператор New</span><span class="sxs-lookup"><span data-stu-id="01191-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="01191-164">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01191-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="01191-165">Тип данных Object</span><span class="sxs-lookup"><span data-stu-id="01191-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="01191-166">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="01191-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="01191-167">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="01191-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="01191-168">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="01191-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="01191-169">Практическое руководство. Использование универсального класса</span><span class="sxs-lookup"><span data-stu-id="01191-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="01191-170">Ковариация и контрвариантность</span><span class="sxs-lookup"><span data-stu-id="01191-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="01191-171">In</span><span class="sxs-lookup"><span data-stu-id="01191-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="01191-172">Out</span><span class="sxs-lookup"><span data-stu-id="01191-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
