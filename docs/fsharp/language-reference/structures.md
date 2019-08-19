---
title: Структуры
description: Сведения о F# структуре. тип объекта Compact часто более эффективен, чем класс для типов с небольшим объемом данных и простым поведением.
ms.date: 05/16/2016
ms.openlocfilehash: e638b450fe43e0993c9980cade246c3f26d25e2d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630772"
---
# <a name="structures"></a><span data-ttu-id="fdda6-103">Структуры</span><span class="sxs-lookup"><span data-stu-id="fdda6-103">Structures</span></span>

<span data-ttu-id="fdda6-104">*Структура* — это тип компактного объекта, который может быть более эффективным, чем класс для типов, имеющих небольшой объем данных и простое поведение.</span><span class="sxs-lookup"><span data-stu-id="fdda6-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="fdda6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fdda6-105">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a><span data-ttu-id="fdda6-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="fdda6-106">Remarks</span></span>

<span data-ttu-id="fdda6-107">Структуры являются *типами значений*. Это означает, что они хранятся непосредственно в стеке или, когда они используются в качестве полей или элементов массива, встроены в родительский тип.</span><span class="sxs-lookup"><span data-stu-id="fdda6-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="fdda6-108">В отличие от классов и записей структуры имеют семантику pass-by-value (передача по значению).</span><span class="sxs-lookup"><span data-stu-id="fdda6-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="fdda6-109">Это означает, что они используются в основном для небольших объемов данных, которые часто используются и копируются.</span><span class="sxs-lookup"><span data-stu-id="fdda6-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="fdda6-110">В предыдущем синтаксисе показаны две формы.</span><span class="sxs-lookup"><span data-stu-id="fdda6-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="fdda6-111">Первая не является упрощенным синтаксисом, но, тем не менее, используется довольно часто, так как при использовании ключевых слов `struct` и `end` можно опустить атрибут `StructAttribute`, который есть во второй форме.</span><span class="sxs-lookup"><span data-stu-id="fdda6-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="fdda6-112">`StructAttribute` можно сократить до `Struct`.</span><span class="sxs-lookup"><span data-stu-id="fdda6-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="fdda6-113">В предыдущем синтаксисе *типы-Definition-Elements-and-Members* представляют объявления и определения членов.</span><span class="sxs-lookup"><span data-stu-id="fdda6-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="fdda6-114">Структуры могут иметь конструкторы, изменяемые и неизменяемые поля. Они также могут объявлять элементы и реализации интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="fdda6-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="fdda6-115">Дополнительные сведения см. в разделе [Members](./members/index.md).</span><span class="sxs-lookup"><span data-stu-id="fdda6-115">For more information, see [Members](./members/index.md).</span></span>

<span data-ttu-id="fdda6-116">Структуры не могут участвовать в наследовании, не могут содержать привязки `let` или `do`, не могут рекурсивно содержать поля собственного типа (хотя могут содержать ссылочные ячейки, которые ссылаются на собственный тип).</span><span class="sxs-lookup"><span data-stu-id="fdda6-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="fdda6-117">Так как структуры не допускают использование привязок `let`, в структурах необходимо объявлять поля с помощью ключевого слова `val`.</span><span class="sxs-lookup"><span data-stu-id="fdda6-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="fdda6-118">Ключевое слово `val` определяет поле и его тип, но не разрешает выполнять инициализацию.</span><span class="sxs-lookup"><span data-stu-id="fdda6-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="fdda6-119">Вместо этого объявления `val` инициализируются с нулем или значением null.</span><span class="sxs-lookup"><span data-stu-id="fdda6-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="fdda6-120">Поэтому для структур с неявным конструктором (то есть параметрами, заданными непосредственно после имени структуры в объявлении) требуется, чтобы объявления `val` были помечены атрибутом `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="fdda6-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="fdda6-121">Структуры, имеющие определенный конструктор, по-прежнему поддерживают инициализацию с нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="fdda6-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="fdda6-122">Таким образом, атрибут `DefaultValue` является объявлением того, что для поля допускается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="fdda6-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="fdda6-123">Неявные конструкторы для структур не выполняют каких-либо действий, так как привязки `let` и `do` не разрешены для типа, однако переданные значения параметров неявного конструктора доступны в виде закрытых полей.</span><span class="sxs-lookup"><span data-stu-id="fdda6-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="fdda6-124">Явные конструкторы могут способствовать инициализации значений полей.</span><span class="sxs-lookup"><span data-stu-id="fdda6-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="fdda6-125">Структура, которая имеет явный конструктор, по-прежнему поддерживают инициализацию с нулевым значением. Тем не менее, в объявлениях `DefaultValue` не следует использовать атрибут `val`, поскольку он вступает в конфликт с явным конструктором.</span><span class="sxs-lookup"><span data-stu-id="fdda6-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="fdda6-126">Дополнительные сведения об `val` объявлениях см. [в разделе явные поля: Ключевое](./members/explicit-fields-the-val-keyword.md)слово. `val`</span><span class="sxs-lookup"><span data-stu-id="fdda6-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="fdda6-127">В структурах допускается использование атрибутов и модификаторов доступности, для которых действуют те же правила, что и для других типов.</span><span class="sxs-lookup"><span data-stu-id="fdda6-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="fdda6-128">Дополнительные сведения см. в разделе [атрибуты](attributes.md) и [Управление доступом](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="fdda6-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="fdda6-129">В следующих примерах кода показаны определения структуры.</span><span class="sxs-lookup"><span data-stu-id="fdda6-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="fdda6-130">Структуры Бирефлике</span><span class="sxs-lookup"><span data-stu-id="fdda6-130">ByRefLike structs</span></span>

<span data-ttu-id="fdda6-131">Вы можете определить собственные структуры, которые могут соответствовать `byref`семантике, приведенной ниже. Дополнительные сведения см. в разделе [ByRef](byrefs.md) .</span><span class="sxs-lookup"><span data-stu-id="fdda6-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="fdda6-132">Это делается с помощью <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> атрибута:</span><span class="sxs-lookup"><span data-stu-id="fdda6-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="fdda6-133">`IsByRefLike`не подразумевается `Struct`.</span><span class="sxs-lookup"><span data-stu-id="fdda6-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="fdda6-134">Оба должны присутствовать в типе.</span><span class="sxs-lookup"><span data-stu-id="fdda6-134">Both must be present on the type.</span></span>

<span data-ttu-id="fdda6-135">"`byref`-Like" структура в F# — это тип значения, привязанный к стеку.</span><span class="sxs-lookup"><span data-stu-id="fdda6-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="fdda6-136">Он никогда не выделяется в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="fdda6-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="fdda6-137">Структура `byref`, похожая на структуру, полезна для высокопроизводительного программирования, так как она применяется с набором строгих проверок на время существования и без записи.</span><span class="sxs-lookup"><span data-stu-id="fdda6-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="fdda6-138">Правила:</span><span class="sxs-lookup"><span data-stu-id="fdda6-138">The rules are:</span></span>

* <span data-ttu-id="fdda6-139">Их можно использовать в качестве параметров функций, параметров методов, локальных переменных, возвращаемых методом.</span><span class="sxs-lookup"><span data-stu-id="fdda6-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="fdda6-140">Они не могут быть статическими или членами экземпляров класса или обычной структуры.</span><span class="sxs-lookup"><span data-stu-id="fdda6-140">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="fdda6-141">Они не могут быть захвачены ни одной конструкцией замыкания (`async` методами или лямбда-выражениями).</span><span class="sxs-lookup"><span data-stu-id="fdda6-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="fdda6-142">Их нельзя использовать в качестве универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="fdda6-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="fdda6-143">Хотя эти правила очень сильно ограничивают использование, они делают это для обеспечения безопасности высокопроизводительных вычислительных систем надежным способом.</span><span class="sxs-lookup"><span data-stu-id="fdda6-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="fdda6-144">Структуры только для чтения</span><span class="sxs-lookup"><span data-stu-id="fdda6-144">ReadOnly structs</span></span>

<span data-ttu-id="fdda6-145">Можно закомментировать структуры с помощью <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="fdda6-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="fdda6-146">Например:</span><span class="sxs-lookup"><span data-stu-id="fdda6-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="fdda6-147">`IsReadOnly`не подразумевается `Struct`.</span><span class="sxs-lookup"><span data-stu-id="fdda6-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="fdda6-148">Необходимо добавить оба варианта, чтобы иметь `IsReadOnly` структуру.</span><span class="sxs-lookup"><span data-stu-id="fdda6-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="fdda6-149">Использование этого атрибута создает метаданные, позволяя F# C# ему обрабатываться как `inref<'T>` и `in ref`соответственно.</span><span class="sxs-lookup"><span data-stu-id="fdda6-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="fdda6-150">Определение изменяемого значения внутри структуры, предназначенной только для чтения, приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="fdda6-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="fdda6-151">Записи структуры и размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="fdda6-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="fdda6-152">[Записи](records.md) и [Размеченные объединения](discriminated-unions.md) можно представить в виде структур с `[<Struct>]` атрибутом.</span><span class="sxs-lookup"><span data-stu-id="fdda6-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="fdda6-153">Дополнительные сведения см. в статье.</span><span class="sxs-lookup"><span data-stu-id="fdda6-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdda6-154">См. также</span><span class="sxs-lookup"><span data-stu-id="fdda6-154">See also</span></span>

- [<span data-ttu-id="fdda6-155">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="fdda6-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="fdda6-156">Классы</span><span class="sxs-lookup"><span data-stu-id="fdda6-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="fdda6-157">Записи</span><span class="sxs-lookup"><span data-stu-id="fdda6-157">Records</span></span>](records.md)
- [<span data-ttu-id="fdda6-158">Члены</span><span class="sxs-lookup"><span data-stu-id="fdda6-158">Members</span></span>](./members/index.md)
