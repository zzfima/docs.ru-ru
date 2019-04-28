---
title: Структуры
description: Дополнительные сведения о F# структуры, это компактный тип объекта часто более эффективен, чем класс для типов с меньшим объемом данных и простое поведение.
ms.date: 05/16/2016
ms.openlocfilehash: c091dc91765d6e828426de21e9bc5f79bfdebc6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925883"
---
# <a name="structures"></a><span data-ttu-id="07365-103">Структуры</span><span class="sxs-lookup"><span data-stu-id="07365-103">Structures</span></span>

<span data-ttu-id="07365-104">Объект *структура* — компактный тип объекта, может оказаться более эффективным, чем класс для типов, имеющих небольшое количество данных и простое поведение.</span><span class="sxs-lookup"><span data-stu-id="07365-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="07365-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07365-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="07365-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="07365-106">Remarks</span></span>

<span data-ttu-id="07365-107">Структуры являются *типы значений*, что означает, что они хранятся непосредственно в стеке или, если они используются в качестве полей или тип элементов массива, внутри родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="07365-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="07365-108">В отличие от классов и записей структуры имеют семантику pass-by-value (передача по значению).</span><span class="sxs-lookup"><span data-stu-id="07365-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="07365-109">Это означает, что они используются в основном для небольших объемов данных, которые часто используются и копируются.</span><span class="sxs-lookup"><span data-stu-id="07365-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="07365-110">В предыдущем синтаксисе показаны две формы.</span><span class="sxs-lookup"><span data-stu-id="07365-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="07365-111">Первая не является упрощенным синтаксисом, но, тем не менее, используется довольно часто, так как при использовании ключевых слов `struct` и `end` можно опустить атрибут `StructAttribute`, который есть во второй форме.</span><span class="sxs-lookup"><span data-stu-id="07365-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="07365-112">`StructAttribute` можно сократить до `Struct`.</span><span class="sxs-lookup"><span data-stu-id="07365-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="07365-113">*-Definition элементов и членов типа* в предыдущем синтаксисе представляет объявления и определения элементов.</span><span class="sxs-lookup"><span data-stu-id="07365-113">The *type-definition-elements-and-members* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="07365-114">Структуры могут иметь конструкторы, изменяемые и неизменяемые поля. Они также могут объявлять элементы и реализации интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="07365-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="07365-115">Дополнительные сведения см. в разделе [члены](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="07365-115">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="07365-116">Структуры не могут участвовать в наследовании, не могут содержать привязки `let` или `do`, не могут рекурсивно содержать поля собственного типа (хотя могут содержать ссылочные ячейки, которые ссылаются на собственный тип).</span><span class="sxs-lookup"><span data-stu-id="07365-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="07365-117">Так как структуры не допускают использование привязок `let`, в структурах необходимо объявлять поля с помощью ключевого слова `val`.</span><span class="sxs-lookup"><span data-stu-id="07365-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="07365-118">Ключевое слово `val` определяет поле и его тип, но не разрешает выполнять инициализацию.</span><span class="sxs-lookup"><span data-stu-id="07365-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="07365-119">Вместо этого объявления `val` инициализируются с нулем или значением null.</span><span class="sxs-lookup"><span data-stu-id="07365-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="07365-120">Поэтому для структур с неявным конструктором (то есть параметрами, заданными непосредственно после имени структуры в объявлении) требуется, чтобы объявления `val` были помечены атрибутом `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="07365-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="07365-121">Структуры, имеющие определенный конструктор, по-прежнему поддерживают инициализацию с нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="07365-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="07365-122">Таким образом, атрибут `DefaultValue` является объявлением того, что для поля допускается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="07365-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="07365-123">Неявные конструкторы для структур не выполняют каких-либо действий, так как привязки `let` и `do` не разрешены для типа, однако переданные значения параметров неявного конструктора доступны в виде закрытых полей.</span><span class="sxs-lookup"><span data-stu-id="07365-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="07365-124">Явные конструкторы могут способствовать инициализации значений полей.</span><span class="sxs-lookup"><span data-stu-id="07365-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="07365-125">Структура, которая имеет явный конструктор, по-прежнему поддерживают инициализацию с нулевым значением. Тем не менее, в объявлениях `DefaultValue` не следует использовать атрибут `val`, поскольку он вступает в конфликт с явным конструктором.</span><span class="sxs-lookup"><span data-stu-id="07365-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="07365-126">Дополнительные сведения о `val` объявления, см. в разделе [явные поля: `val` Ключевое слово](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="07365-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="07365-127">В структурах допускается использование атрибутов и модификаторов доступности, для которых действуют те же правила, что и для других типов.</span><span class="sxs-lookup"><span data-stu-id="07365-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="07365-128">Дополнительные сведения см. в разделе [атрибуты](attributes.md) и [контроля доступа](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="07365-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="07365-129">В следующих примерах кода показаны определения структуры.</span><span class="sxs-lookup"><span data-stu-id="07365-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a><span data-ttu-id="07365-130">ByRefLike структуры</span><span class="sxs-lookup"><span data-stu-id="07365-130">ByRefLike structs</span></span>

<span data-ttu-id="07365-131">Вы можете определить собственные структуры, можно придерживаться `byref`-семантику, например: см. в разделе [Byrefs](byrefs.md) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="07365-131">You can define your own structs that can adhere to `byref`-like semantics: see [Byrefs](byrefs.md) for more information.</span></span> <span data-ttu-id="07365-132">Это делается с помощью <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> атрибут:</span><span class="sxs-lookup"><span data-stu-id="07365-132">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="07365-133">`IsByRefLike` не подразумевает `Struct`.</span><span class="sxs-lookup"><span data-stu-id="07365-133">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="07365-134">Оба должны присутствовать на тип.</span><span class="sxs-lookup"><span data-stu-id="07365-134">Both must be present on the type.</span></span>

<span data-ttu-id="07365-135">Объект "`byref`-как «структура в F# является типом значения стека привязки.</span><span class="sxs-lookup"><span data-stu-id="07365-135">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="07365-136">Он никогда не выделяется в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="07365-136">It is never allocated on the managed heap.</span></span> <span data-ttu-id="07365-137">Объект `byref`-как структура полезна для программирования высокой производительности, как реализована с помощью набора строгим проверкам, о времени существования и незахвата.</span><span class="sxs-lookup"><span data-stu-id="07365-137">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="07365-138">Ниже приведены правила.</span><span class="sxs-lookup"><span data-stu-id="07365-138">The rules are:</span></span>

* <span data-ttu-id="07365-139">Они могут использоваться как параметры функции, параметры метода, локальные переменные, метод возвращает.</span><span class="sxs-lookup"><span data-stu-id="07365-139">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="07365-140">Они не может быть статическим или члены класса или обычной структуры экземпляров.</span><span class="sxs-lookup"><span data-stu-id="07365-140">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="07365-141">Не может быть перехвачено любой конструкции замыкание (`async` методы или лямбда-выражений).</span><span class="sxs-lookup"><span data-stu-id="07365-141">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="07365-142">Они не может использоваться в качестве универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="07365-142">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="07365-143">Несмотря на то, что эти правила очень строго ограничить использование, они появляющимися достигается за счет высокопроизводительные вычислительные системы безопасным образом.</span><span class="sxs-lookup"><span data-stu-id="07365-143">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="07365-144">Структурах только для чтения</span><span class="sxs-lookup"><span data-stu-id="07365-144">ReadOnly structs</span></span>

<span data-ttu-id="07365-145">Можно добавить заметку структуры <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="07365-145">You can annotate structs with the <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> attribute.</span></span> <span data-ttu-id="07365-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="07365-146">For example:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="07365-147">`IsReadOnly` не подразумевает `Struct`.</span><span class="sxs-lookup"><span data-stu-id="07365-147">`IsReadOnly` does not imply `Struct`.</span></span> <span data-ttu-id="07365-148">Необходимо добавить оба иметь `IsReadOnly` структуры.</span><span class="sxs-lookup"><span data-stu-id="07365-148">You must add both to have an `IsReadOnly` struct.</span></span>

<span data-ttu-id="07365-149">Использование этого атрибута выдает предоставления метаданных F# и C# знать, что `inref<'T>` и `in ref`, соответственно.</span><span class="sxs-lookup"><span data-stu-id="07365-149">Use of this attribute emits metadata letting F# and C# know to treat it as `inref<'T>` and `in ref`, respectively.</span></span>

<span data-ttu-id="07365-150">Определение изменяемого значения внутри структуры только для чтения выводит сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="07365-150">Defining a mutable value inside of a readonly struct produces an error.</span></span>

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="07365-151">Структура записи и размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="07365-151">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="07365-152">Вы можете представить [записей](records.md) и [размеченные объединения](discriminated-unions.md) как структуры с `[<Struct>]` атрибута.</span><span class="sxs-lookup"><span data-stu-id="07365-152">You can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="07365-153">См. в каждой статье для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="07365-153">See each article to learn more.</span></span>

## <a name="see-also"></a><span data-ttu-id="07365-154">См. также</span><span class="sxs-lookup"><span data-stu-id="07365-154">See also</span></span>

- [<span data-ttu-id="07365-155">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="07365-155">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="07365-156">Классы</span><span class="sxs-lookup"><span data-stu-id="07365-156">Classes</span></span>](classes.md)
- [<span data-ttu-id="07365-157">Записи</span><span class="sxs-lookup"><span data-stu-id="07365-157">Records</span></span>](records.md)
- [<span data-ttu-id="07365-158">Члены</span><span class="sxs-lookup"><span data-stu-id="07365-158">Members</span></span>](members/index.md)