---
title: Partial
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: df85571b757fd54496677bad1195fab9690b79cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351362"
---
# <a name="partial-visual-basic"></a><span data-ttu-id="23045-102">Partial (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23045-102">Partial (Visual Basic)</span></span>
<span data-ttu-id="23045-103">Указывает, что объявление типа — это частичное определение типа.</span><span class="sxs-lookup"><span data-stu-id="23045-103">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="23045-104">Вы можете разделить определение типа среди нескольких объявлений, используя ключевое слово `Partial`.</span><span class="sxs-lookup"><span data-stu-id="23045-104">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="23045-105">Можно использовать столько частичных объявлений, сколько необходимо, во множестве исходных файлах.</span><span class="sxs-lookup"><span data-stu-id="23045-105">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="23045-106">Однако все объявления должны находиться в одной сборке и одном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="23045-106">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23045-107">Visual Basic поддерживает *разделяемые методы*, которые обычно реализуются в разделяемых классах.</span><span class="sxs-lookup"><span data-stu-id="23045-107">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="23045-108">Дополнительные сведения см. в разделе [разделяемые методы](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) и [подоператоры](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="23045-108">For more information, see [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23045-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23045-109">Syntax</span></span>  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="23045-110">Части</span><span class="sxs-lookup"><span data-stu-id="23045-110">Parts</span></span>  
  
|<span data-ttu-id="23045-111">Термин</span><span class="sxs-lookup"><span data-stu-id="23045-111">Term</span></span>|<span data-ttu-id="23045-112">Определение</span><span class="sxs-lookup"><span data-stu-id="23045-112">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="23045-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-113">Optional.</span></span> <span data-ttu-id="23045-114">Список атрибутов, применяемых к этому событию.</span><span class="sxs-lookup"><span data-stu-id="23045-114">List of attributes that apply to this type.</span></span> <span data-ttu-id="23045-115">[Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md) необходимо заключить в угловые скобки (`< >`).</span><span class="sxs-lookup"><span data-stu-id="23045-115">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="23045-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-116">Optional.</span></span> <span data-ttu-id="23045-117">Указывает, какой код может получить доступ к этому событию.</span><span class="sxs-lookup"><span data-stu-id="23045-117">Specifies what code can access this type.</span></span> <span data-ttu-id="23045-118">См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="23045-118">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="23045-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-119">Optional.</span></span> <span data-ttu-id="23045-120">См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="23045-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="23045-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-121">Optional.</span></span> <span data-ttu-id="23045-122">См. раздел [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="23045-122">See [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="23045-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-123">Optional.</span></span> <span data-ttu-id="23045-124">См. [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span><span class="sxs-lookup"><span data-stu-id="23045-124">See [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="23045-125">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="23045-125">Required.</span></span> <span data-ttu-id="23045-126">Имя данного типа.</span><span class="sxs-lookup"><span data-stu-id="23045-126">Name of this type.</span></span> <span data-ttu-id="23045-127">Оно должно соответствовать имени, определенному в других частичных объявлениях того же типа.</span><span class="sxs-lookup"><span data-stu-id="23045-127">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="23045-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-128">Optional.</span></span> <span data-ttu-id="23045-129">Указывает, что это универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="23045-129">Specifies that this is a generic type.</span></span> <span data-ttu-id="23045-130">См. раздел [универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="23045-130">See [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="23045-131">Требуется [, если используется.](../../../visual-basic/language-reference/statements/of-clause.md)</span><span class="sxs-lookup"><span data-stu-id="23045-131">Required if you use [Of](../../../visual-basic/language-reference/statements/of-clause.md).</span></span> <span data-ttu-id="23045-132">См. [список типов](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="23045-132">See [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="23045-133">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-133">Optional.</span></span> <span data-ttu-id="23045-134">См. раздел [оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).</span><span class="sxs-lookup"><span data-stu-id="23045-134">See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="23045-135">Обязательный параметр, если используется параметр `Inherits`.</span><span class="sxs-lookup"><span data-stu-id="23045-135">Required if you use `Inherits`.</span></span> <span data-ttu-id="23045-136">Имя класса или интерфейса, от которого наследует этот класс.</span><span class="sxs-lookup"><span data-stu-id="23045-136">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="23045-137">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-137">Optional.</span></span> <span data-ttu-id="23045-138">См. [инструкцию Implements](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="23045-138">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="23045-139">Обязательный параметр, если используется параметр `Implements`.</span><span class="sxs-lookup"><span data-stu-id="23045-139">Required if you use `Implements`.</span></span> <span data-ttu-id="23045-140">Имена интерфейсов, реализуемых этим типом.</span><span class="sxs-lookup"><span data-stu-id="23045-140">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="23045-141">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-141">Optional.</span></span> <span data-ttu-id="23045-142">Операторы, которые объявляют дополнительные переменные и события для типа.</span><span class="sxs-lookup"><span data-stu-id="23045-142">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="23045-143">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="23045-143">Optional.</span></span> <span data-ttu-id="23045-144">Операторы, которые объявляют и определяют дополнительные процедуры для типа.</span><span class="sxs-lookup"><span data-stu-id="23045-144">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="23045-145">`End Class` или `End Structure`</span><span class="sxs-lookup"><span data-stu-id="23045-145">`End Class` or `End Structure`</span></span>|<span data-ttu-id="23045-146">Завершает этот частичное определение `Class` или `Structure`.</span><span class="sxs-lookup"><span data-stu-id="23045-146">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23045-147">Примечания</span><span class="sxs-lookup"><span data-stu-id="23045-147">Remarks</span></span>  
 <span data-ttu-id="23045-148">Visual Basic использует разделяемые определения класса для разделения автоматически созданного кода и пользовательского кода в по отдельным файлам исходного кода.</span><span class="sxs-lookup"><span data-stu-id="23045-148">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="23045-149">Например, **конструктор форм Windows Forms** определяет разделяемые классы для элементов управления, таких как <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="23045-149">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="23045-150">Не следует изменять код, созданный в этих элементах управления.</span><span class="sxs-lookup"><span data-stu-id="23045-150">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="23045-151">Все правила для создания класса, структуры, интерфейса и модуля, например для использования модификатора и наследования, применяются при создании частичного типа.</span><span class="sxs-lookup"><span data-stu-id="23045-151">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="23045-152">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="23045-152">Best Practices</span></span>  
  
- <span data-ttu-id="23045-153">В обычных условиях не следует разбивать один тип на два или более объявлений.</span><span class="sxs-lookup"><span data-stu-id="23045-153">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="23045-154">Поэтому в большинстве случаев ключевое `Partial` слово не требуется.</span><span class="sxs-lookup"><span data-stu-id="23045-154">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
- <span data-ttu-id="23045-155">Для удобочитаемости каждое частичное объявление типа должно включать ключевое слово `Partial`.</span><span class="sxs-lookup"><span data-stu-id="23045-155">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="23045-156">Компилятор позволяет пропускать ключевое слово только в одном частичном объявлении. Если это происходит в двух или более объявлениях, компилятор сообщает об ошибке.</span><span class="sxs-lookup"><span data-stu-id="23045-156">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="23045-157">Поведение</span><span class="sxs-lookup"><span data-stu-id="23045-157">Behavior</span></span>  
  
- <span data-ttu-id="23045-158">**Объединение объявлений.**</span><span class="sxs-lookup"><span data-stu-id="23045-158">**Union of Declarations.**</span></span> <span data-ttu-id="23045-159">Компилятор рассматривает тип как объединение всех его частичных объявлений.</span><span class="sxs-lookup"><span data-stu-id="23045-159">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="23045-160">Каждый модификатор из каждого частичного определения применяется ко всему типу, а каждый элемент из каждого частичного определения доступен для всего типа.</span><span class="sxs-lookup"><span data-stu-id="23045-160">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
- <span data-ttu-id="23045-161">**Повышение типа не допускается для разделяемых типов в модулях.**</span><span class="sxs-lookup"><span data-stu-id="23045-161">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="23045-162">Если частичное определение находится внутри модуля, повышение типа этого типа автоматически отменяется.</span><span class="sxs-lookup"><span data-stu-id="23045-162">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="23045-163">В таком случае набор частичных определений может привести к непредсказуемым результатам и даже ошибкам компилятора.</span><span class="sxs-lookup"><span data-stu-id="23045-163">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="23045-164">Дополнительные сведения см. в разделе [повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span><span class="sxs-lookup"><span data-stu-id="23045-164">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="23045-165">Компилятор объединяет частичные определения, только если их полные пути идентичны.</span><span class="sxs-lookup"><span data-stu-id="23045-165">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="23045-166">Ключевое слово `Partial` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="23045-166">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="23045-167">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="23045-167">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="23045-168">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="23045-168">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="23045-169">Пример</span><span class="sxs-lookup"><span data-stu-id="23045-169">Example</span></span>  
 <span data-ttu-id="23045-170">Следующий пример разделяет определение класса `sampleClass` на два объявления, в каждом из которых определяется отдельная процедура `Sub`.</span><span class="sxs-lookup"><span data-stu-id="23045-170">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 <span data-ttu-id="23045-171">Два частичных определения в предыдущем примере могут находиться в одном или двух исходных файлах.</span><span class="sxs-lookup"><span data-stu-id="23045-171">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23045-172">См. также</span><span class="sxs-lookup"><span data-stu-id="23045-172">See also</span></span>

- [<span data-ttu-id="23045-173">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="23045-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="23045-174">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="23045-174">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="23045-175">Повышение типа</span><span class="sxs-lookup"><span data-stu-id="23045-175">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [<span data-ttu-id="23045-176">Shadows</span><span class="sxs-lookup"><span data-stu-id="23045-176">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="23045-177">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="23045-177">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="23045-178">Разделяемые методы</span><span class="sxs-lookup"><span data-stu-id="23045-178">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
