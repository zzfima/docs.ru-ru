---
title: Shared
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
ms.openlocfilehash: 98fa25d2283408dfb80e82fbc620a1b284e5c530
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349117"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="42165-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42165-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="42165-103">Указывает, что один или несколько объявленных программных элементов связаны с классом или структурой в большом объеме, а не с конкретным экземпляром класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="42165-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42165-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="42165-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="42165-105">Когда следует использовать Shared</span><span class="sxs-lookup"><span data-stu-id="42165-105">When to Use Shared</span></span>  
 <span data-ttu-id="42165-106">Совместное использование члена класса или структуры делает его доступным для каждого экземпляра, а не для *совместного использования*, где каждый экземпляр хранит собственную копию.</span><span class="sxs-lookup"><span data-stu-id="42165-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="42165-107">Это полезно, например, если значение переменной применяется ко всему приложению.</span><span class="sxs-lookup"><span data-stu-id="42165-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="42165-108">Если объявить эту переменную для `Shared`, то все экземпляры будут обращаться к тому же месту хранения, и если один экземпляр изменит значение переменной, то все экземпляры получают доступ к обновленному значению.</span><span class="sxs-lookup"><span data-stu-id="42165-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="42165-109">Совместное использование не изменяет уровень доступа элемента.</span><span class="sxs-lookup"><span data-stu-id="42165-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="42165-110">Например, член класса может быть общим и частным (доступным только в пределах класса), а также не является общим и общим.</span><span class="sxs-lookup"><span data-stu-id="42165-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="42165-111">Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="42165-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="42165-112">Правила</span><span class="sxs-lookup"><span data-stu-id="42165-112">Rules</span></span>  
  
- <span data-ttu-id="42165-113">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="42165-113">**Declaration Context.**</span></span> <span data-ttu-id="42165-114">`Shared` можно использовать только на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="42165-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="42165-115">Это означает, что контекст объявления для элемента `Shared` должен быть классом или структурой и не может быть исходным файлом, пространством имен или процедурой.</span><span class="sxs-lookup"><span data-stu-id="42165-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="42165-116">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="42165-116">**Combined Modifiers.**</span></span> <span data-ttu-id="42165-117">В одном объявлении нельзя указывать `Shared` вместе с [переопределениями](../../../visual-basic/language-reference/modifiers/overrides.md), [переопределяемыми](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)или [static](../../../visual-basic/language-reference/modifiers/static.md) .</span><span class="sxs-lookup"><span data-stu-id="42165-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
- <span data-ttu-id="42165-118">**Данному.**</span><span class="sxs-lookup"><span data-stu-id="42165-118">**Accessing.**</span></span> <span data-ttu-id="42165-119">Доступ к общему элементу осуществляется путем указания его имени класса или структуры, а не имени переменной определенного экземпляра его класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="42165-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="42165-120">Вам даже не нужно создавать экземпляр класса или структуры для доступа к его общим членам.</span><span class="sxs-lookup"><span data-stu-id="42165-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="42165-121">В следующем примере вызывается общая процедура <xref:System.Double.IsNaN%2A> предоставляемой структурой <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="42165-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- <span data-ttu-id="42165-122">**Неявный общий доступ.**</span><span class="sxs-lookup"><span data-stu-id="42165-122">**Implicit Sharing.**</span></span> <span data-ttu-id="42165-123">Нельзя использовать модификатор `Shared` в [операторе const](../../../visual-basic/language-reference/statements/const-statement.md), но константы неявно являются общими.</span><span class="sxs-lookup"><span data-stu-id="42165-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="42165-124">Аналогичным образом нельзя объявить член модуля или интерфейса для `Shared`, но они являются неявно общими.</span><span class="sxs-lookup"><span data-stu-id="42165-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="42165-125">Поведение</span><span class="sxs-lookup"><span data-stu-id="42165-125">Behavior</span></span>  
  
- <span data-ttu-id="42165-126">**Объема.**</span><span class="sxs-lookup"><span data-stu-id="42165-126">**Storage.**</span></span> <span data-ttu-id="42165-127">Общая переменная или событие хранится в памяти только один раз, независимо от того, сколько экземпляров вы создаете его класс или структуру.</span><span class="sxs-lookup"><span data-stu-id="42165-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="42165-128">Аналогично, Общая процедура или свойство содержит только один набор локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="42165-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
- <span data-ttu-id="42165-129">**Доступ через переменную экземпляра.**</span><span class="sxs-lookup"><span data-stu-id="42165-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="42165-130">Доступ к общему элементу можно получить, добавив в него имя переменной, содержащей конкретный экземпляр его класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="42165-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="42165-131">Несмотря на то, что обычно работает, как и ожидалось, компилятор создает предупреждающее сообщение и предоставляет доступ через имя класса или структуры вместо переменной.</span><span class="sxs-lookup"><span data-stu-id="42165-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
- <span data-ttu-id="42165-132">**Доступ через выражение экземпляра.**</span><span class="sxs-lookup"><span data-stu-id="42165-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="42165-133">При доступе к общему элементу с помощью выражения, возвращающего экземпляр класса или структуры, компилятор делает доступ через имя класса или структуры вместо вычисления выражения.</span><span class="sxs-lookup"><span data-stu-id="42165-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="42165-134">Это приводит к непредвиденным результатам, если выражение предназначено для выполнения других действий, а также для возврата экземпляра.</span><span class="sxs-lookup"><span data-stu-id="42165-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="42165-135">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="42165-135">The following example illustrates this.</span></span>  
  
    ```vb
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
  
     <span data-ttu-id="42165-136">В предыдущем примере компилятор выдает предупреждающее сообщение в обоих случаях, когда код обращается к общей переменной `total` через экземпляр.</span><span class="sxs-lookup"><span data-stu-id="42165-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="42165-137">В каждом случае доступ осуществляется напрямую через класс `shareTotal` и не используется ни один экземпляр.</span><span class="sxs-lookup"><span data-stu-id="42165-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="42165-138">В случае предполагаемого вызова процедуры `returnClass`это означает, что он даже не создает вызов `returnClass`, поэтому дополнительное действие отображения "Function Ретурнкласс ()" не выполняется.</span><span class="sxs-lookup"><span data-stu-id="42165-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="42165-139">Модификатор `Shared` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="42165-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="42165-140">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="42165-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="42165-141">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="42165-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="42165-142">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="42165-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="42165-143">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="42165-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="42165-144">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="42165-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="42165-145">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="42165-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="42165-146">См. также</span><span class="sxs-lookup"><span data-stu-id="42165-146">See also</span></span>

- [<span data-ttu-id="42165-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="42165-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="42165-148">Статические</span><span class="sxs-lookup"><span data-stu-id="42165-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="42165-149">Время существования в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="42165-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="42165-150">Процедуры</span><span class="sxs-lookup"><span data-stu-id="42165-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="42165-151">Структуры</span><span class="sxs-lookup"><span data-stu-id="42165-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="42165-152">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="42165-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
