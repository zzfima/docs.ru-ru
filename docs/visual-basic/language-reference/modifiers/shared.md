---
title: Shared (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: b15dd08d69f372317b9140001e8072eeb66d44ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="shared-visual-basic"></a><span data-ttu-id="d06d6-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d06d6-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="d06d6-103">Указывает, что один или несколько объявленных программных элементов связаны с классом или структурой целиком, а не с определенным экземпляром класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d06d6-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d06d6-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="d06d6-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="d06d6-105">Когда следует использовать Shared</span><span class="sxs-lookup"><span data-stu-id="d06d6-105">When to Use Shared</span></span>  
 <span data-ttu-id="d06d6-106">Совместное использование членов класса или структуры делает ее доступной для каждого экземпляра, а не *не совместно*, где каждый экземпляр хранит собственную копию.</span><span class="sxs-lookup"><span data-stu-id="d06d6-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="d06d6-107">Это полезно, например, если значение переменной используется для всего приложения.</span><span class="sxs-lookup"><span data-stu-id="d06d6-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="d06d6-108">Если объявить эту переменную как `Shared`, затем все экземпляры доступа место хранения и доступа, если один экземпляр изменяет значение переменной, все экземпляры обновленное значение.</span><span class="sxs-lookup"><span data-stu-id="d06d6-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="d06d6-109">Совместное использование не изменяет уровень доступа члена.</span><span class="sxs-lookup"><span data-stu-id="d06d6-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="d06d6-110">Например, член класса можно использовать совместно и private (доступен только в пределах класса), или открытый, так и не используемые совместно.</span><span class="sxs-lookup"><span data-stu-id="d06d6-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="d06d6-111">Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d06d6-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d06d6-112">Правила</span><span class="sxs-lookup"><span data-stu-id="d06d6-112">Rules</span></span>  
  
-   <span data-ttu-id="d06d6-113">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="d06d6-113">**Declaration Context.**</span></span> <span data-ttu-id="d06d6-114">`Shared` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="d06d6-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="d06d6-115">Это означает, что контекст объявления для `Shared` элемент должен быть классом или структурой и не может быть исходным файлом, пространством имен или процедуры.</span><span class="sxs-lookup"><span data-stu-id="d06d6-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="d06d6-116">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="d06d6-116">**Combined Modifiers.**</span></span> <span data-ttu-id="d06d6-117">Нельзя указать `Shared` вместе с [переопределяет](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), или [ Статические](../../../visual-basic/language-reference/modifiers/static.md) в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="d06d6-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
-   <span data-ttu-id="d06d6-118">**Доступ к.**</span><span class="sxs-lookup"><span data-stu-id="d06d6-118">**Accessing.**</span></span> <span data-ttu-id="d06d6-119">Доступ к совместно используемому элементу путем указания имени класса или структуры, не с именем переменной определенного экземпляра класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d06d6-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="d06d6-120">Вы даже нет для создания экземпляра класса или структуры для доступа к его общие члены.</span><span class="sxs-lookup"><span data-stu-id="d06d6-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="d06d6-121">В следующем примере вызывается общую процедуру <xref:System.Double.IsNaN%2A> предоставляемые <xref:System.Double> структуры.</span><span class="sxs-lookup"><span data-stu-id="d06d6-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   <span data-ttu-id="d06d6-122">**Неявное совместное использование данных.**</span><span class="sxs-lookup"><span data-stu-id="d06d6-122">**Implicit Sharing.**</span></span> <span data-ttu-id="d06d6-123">Нельзя использовать `Shared` модификатора [оператор Const](../../../visual-basic/language-reference/statements/const-statement.md), но константы неявно являются общими.</span><span class="sxs-lookup"><span data-stu-id="d06d6-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="d06d6-124">Аналогичным образом, нельзя объявлять член модуля или интерфейса быть `Shared`, но они являются общими неявно.</span><span class="sxs-lookup"><span data-stu-id="d06d6-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d06d6-125">Поведение</span><span class="sxs-lookup"><span data-stu-id="d06d6-125">Behavior</span></span>  
  
-   <span data-ttu-id="d06d6-126">**хранилище.**</span><span class="sxs-lookup"><span data-stu-id="d06d6-126">**Storage.**</span></span> <span data-ttu-id="d06d6-127">Общая переменная или событие сохраняется в памяти только один раз, независимо от того, сколько экземпляров, создайте его класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d06d6-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="d06d6-128">Аналогичным образом общая процедура или свойство содержат только один набор локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="d06d6-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
-   <span data-ttu-id="d06d6-129">**Доступ через переменную экземпляра.**</span><span class="sxs-lookup"><span data-stu-id="d06d6-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="d06d6-130">Можно получить доступ к совместно используемому элементу, указав его с именем переменной, которая содержит экземпляр класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="d06d6-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="d06d6-131">Несмотря на то, что это обычно работает ожидаемым образом, компилятор выдает предупреждающее сообщение и доступ через имя класса или структуры, а не переменной.</span><span class="sxs-lookup"><span data-stu-id="d06d6-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
-   <span data-ttu-id="d06d6-132">**Доступ через экземпляр выражения.**</span><span class="sxs-lookup"><span data-stu-id="d06d6-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="d06d6-133">Если доступ к совместно используемому элементу осуществляется через выражение, возвращающее экземпляр его класса или структуры, компилятор осуществляет доступ с помощью имени класса или структуры, а не оценки выражения.</span><span class="sxs-lookup"><span data-stu-id="d06d6-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="d06d6-134">Это приводит к непредвиденным результатам, если предполагалось использовать выражение для выполнения других действий, а также возврат экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d06d6-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="d06d6-135">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d06d6-135">The following example illustrates this.</span></span>  
  
    ```  
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     <span data-ttu-id="d06d6-136">В предыдущем примере, компилятор создает предупреждение оба раза код обращается к общей переменной `total` через экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d06d6-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="d06d6-137">В каждом случае он осуществляет доступ непосредственно через класс `shareTotal` и не вносит в него экземпляры.</span><span class="sxs-lookup"><span data-stu-id="d06d6-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="d06d6-138">В случае предполагаемого вызова процедуры `returnClass`, это означает, что она даже не создает вызов `returnClass`, поэтому дополнительные действия для отображения «Вызывается функция returnClass()» не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d06d6-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="d06d6-139">Модификатор `Shared` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="d06d6-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d06d6-140">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="d06d6-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="d06d6-141">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="d06d6-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="d06d6-142">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="d06d6-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="d06d6-143">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="d06d6-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="d06d6-144">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="d06d6-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="d06d6-145">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="d06d6-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d06d6-146">См. также</span><span class="sxs-lookup"><span data-stu-id="d06d6-146">See Also</span></span>  
 [<span data-ttu-id="d06d6-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="d06d6-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="d06d6-148">Статические</span><span class="sxs-lookup"><span data-stu-id="d06d6-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)  
 [<span data-ttu-id="d06d6-149">Время существования в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d06d6-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="d06d6-150">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d06d6-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="d06d6-151">Структуры</span><span class="sxs-lookup"><span data-stu-id="d06d6-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="d06d6-152">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="d06d6-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
