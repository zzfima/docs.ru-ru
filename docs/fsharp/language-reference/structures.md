---
title: "Структуры (F#)"
description: "Дополнительные сведения о структуре F #, это компактный тип объекта часто более эффективен, чем класс для типов с помощью небольшого количества данных и простое поведение."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a><span data-ttu-id="1a895-104">Структуры</span><span class="sxs-lookup"><span data-stu-id="1a895-104">Structures</span></span>

<span data-ttu-id="1a895-105">Объект *структура* — компактный тип объекта, может оказаться более эффективным, чем класс для типов, имеющих небольшое количество данных и простое поведение.</span><span class="sxs-lookup"><span data-stu-id="1a895-105">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a895-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a895-106">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a><span data-ttu-id="1a895-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a895-107">Remarks</span></span>
<span data-ttu-id="1a895-108">Структуры являются *типы значений*, что означает, что они хранятся непосредственно в стеке или, если они используются как поля или элементы массива, внутри родительского типа.</span><span class="sxs-lookup"><span data-stu-id="1a895-108">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="1a895-109">В отличие от классов и записей структуры имеют семантику pass-by-value (передача по значению).</span><span class="sxs-lookup"><span data-stu-id="1a895-109">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="1a895-110">Это означает, что они используются в основном для небольших объемов данных, которые часто используются и копируются.</span><span class="sxs-lookup"><span data-stu-id="1a895-110">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="1a895-111">В предыдущем синтаксисе показаны две формы.</span><span class="sxs-lookup"><span data-stu-id="1a895-111">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="1a895-112">Первая не является упрощенным синтаксисом, но, тем не менее, используется довольно часто, так как при использовании ключевых слов `struct` и `end` можно опустить атрибут `StructAttribute`, который есть во второй форме.</span><span class="sxs-lookup"><span data-stu-id="1a895-112">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="1a895-113">`StructAttribute` можно сократить до `Struct`.</span><span class="sxs-lookup"><span data-stu-id="1a895-113">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="1a895-114">*Элементы определения типа* в предыдущем синтаксисе представляет объявления и определения элементов.</span><span class="sxs-lookup"><span data-stu-id="1a895-114">The *type-definition-elements* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="1a895-115">Структуры могут иметь конструкторы, изменяемые и неизменяемые поля. Они также могут объявлять элементы и реализации интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="1a895-115">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="1a895-116">Дополнительные сведения см. в разделе [элементы](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="1a895-116">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="1a895-117">Структуры не могут участвовать в наследовании, не могут содержать привязки `let` или `do`, не могут рекурсивно содержать поля собственного типа (хотя могут содержать ссылочные ячейки, которые ссылаются на собственный тип).</span><span class="sxs-lookup"><span data-stu-id="1a895-117">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="1a895-118">Так как структуры не допускают использование привязок `let`, в структурах необходимо объявлять поля с помощью ключевого слова `val`.</span><span class="sxs-lookup"><span data-stu-id="1a895-118">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="1a895-119">Ключевое слово `val` определяет поле и его тип, но не разрешает выполнять инициализацию.</span><span class="sxs-lookup"><span data-stu-id="1a895-119">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="1a895-120">Вместо этого объявления `val` инициализируются с нулем или значением null.</span><span class="sxs-lookup"><span data-stu-id="1a895-120">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="1a895-121">Поэтому для структур с неявным конструктором (то есть параметрами, заданными непосредственно после имени структуры в объявлении) требуется, чтобы объявления `val` были помечены атрибутом `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="1a895-121">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="1a895-122">Структуры, имеющие определенный конструктор, по-прежнему поддерживают инициализацию с нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="1a895-122">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="1a895-123">Таким образом, атрибут `DefaultValue` является объявлением того, что для поля допускается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="1a895-123">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="1a895-124">Неявные конструкторы для структур не выполняют каких-либо действий, так как привязки `let` и `do` не разрешены для типа, однако переданные значения параметров неявного конструктора доступны в виде закрытых полей.</span><span class="sxs-lookup"><span data-stu-id="1a895-124">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="1a895-125">Явные конструкторы могут способствовать инициализации значений полей.</span><span class="sxs-lookup"><span data-stu-id="1a895-125">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="1a895-126">Структура, которая имеет явный конструктор, по-прежнему поддерживают инициализацию с нулевым значением. Тем не менее, в объявлениях `DefaultValue` не следует использовать атрибут `val`, поскольку он вступает в конфликт с явным конструктором.</span><span class="sxs-lookup"><span data-stu-id="1a895-126">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="1a895-127">Дополнительные сведения о `val` объявления, в разделе [явные поля: `val` ключевое слово](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="1a895-127">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="1a895-128">В структурах допускается использование атрибутов и модификаторов доступности, для которых действуют те же правила, что и для других типов.</span><span class="sxs-lookup"><span data-stu-id="1a895-128">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="1a895-129">Дополнительные сведения см. в разделе [атрибуты](attributes.md) и [управления доступом](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="1a895-129">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="1a895-130">В следующих примерах кода показаны определения структуры.</span><span class="sxs-lookup"><span data-stu-id="1a895-130">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="1a895-131">Структура записи и размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="1a895-131">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="1a895-132">Начиная с версии 4.1 F #, может представлять [записей](records.md) и [размеченные объединения](discriminated-unions.md) как структуры с `[<Struct>]` атрибута.</span><span class="sxs-lookup"><span data-stu-id="1a895-132">Starting with F# 4.1, you can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="1a895-133">Каждой статье для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="1a895-133">See each article to learn more.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1a895-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1a895-134">See Also</span></span>
[<span data-ttu-id="1a895-135">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="1a895-135">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="1a895-136">Классы</span><span class="sxs-lookup"><span data-stu-id="1a895-136">Classes</span></span>](classes.md)

[<span data-ttu-id="1a895-137">Записи</span><span class="sxs-lookup"><span data-stu-id="1a895-137">Records</span></span>](records.md)

[<span data-ttu-id="1a895-138">Члены</span><span class="sxs-lookup"><span data-stu-id="1a895-138">Members</span></span>](members/index.md)
