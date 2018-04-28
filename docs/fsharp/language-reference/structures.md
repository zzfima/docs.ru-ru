---
title: Структуры (F#)
description: 'Дополнительные сведения о структуре F #, это компактный тип объекта часто более эффективен, чем класс для типов с помощью небольшого количества данных и простое поведение.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 14a4799b13c40e363dd400f7effd53264acc5614
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="structures"></a><span data-ttu-id="cfab2-103">Структуры</span><span class="sxs-lookup"><span data-stu-id="cfab2-103">Structures</span></span>

<span data-ttu-id="cfab2-104">Объект *структура* — компактный тип объекта, может оказаться более эффективным, чем класс для типов, имеющих небольшое количество данных и простое поведение.</span><span class="sxs-lookup"><span data-stu-id="cfab2-104">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfab2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfab2-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="cfab2-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="cfab2-106">Remarks</span></span>
<span data-ttu-id="cfab2-107">Структуры являются *типы значений*, что означает, что они хранятся непосредственно в стеке или, если они используются как поля или элементы массива, внутри родительского типа.</span><span class="sxs-lookup"><span data-stu-id="cfab2-107">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="cfab2-108">В отличие от классов и записей структуры имеют семантику pass-by-value (передача по значению).</span><span class="sxs-lookup"><span data-stu-id="cfab2-108">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="cfab2-109">Это означает, что они используются в основном для небольших объемов данных, которые часто используются и копируются.</span><span class="sxs-lookup"><span data-stu-id="cfab2-109">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="cfab2-110">В предыдущем синтаксисе показаны две формы.</span><span class="sxs-lookup"><span data-stu-id="cfab2-110">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="cfab2-111">Первая не является упрощенным синтаксисом, но, тем не менее, используется довольно часто, так как при использовании ключевых слов `struct` и `end` можно опустить атрибут `StructAttribute`, который есть во второй форме.</span><span class="sxs-lookup"><span data-stu-id="cfab2-111">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="cfab2-112">`StructAttribute` можно сократить до `Struct`.</span><span class="sxs-lookup"><span data-stu-id="cfab2-112">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="cfab2-113">*Элементы определения типа* в предыдущем синтаксисе представляет объявления и определения элементов.</span><span class="sxs-lookup"><span data-stu-id="cfab2-113">The *type-definition-elements* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="cfab2-114">Структуры могут иметь конструкторы, изменяемые и неизменяемые поля. Они также могут объявлять элементы и реализации интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="cfab2-114">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="cfab2-115">Дополнительные сведения см. в разделе [элементы](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="cfab2-115">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="cfab2-116">Структуры не могут участвовать в наследовании, не могут содержать привязки `let` или `do`, не могут рекурсивно содержать поля собственного типа (хотя могут содержать ссылочные ячейки, которые ссылаются на собственный тип).</span><span class="sxs-lookup"><span data-stu-id="cfab2-116">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="cfab2-117">Так как структуры не допускают использование привязок `let`, в структурах необходимо объявлять поля с помощью ключевого слова `val`.</span><span class="sxs-lookup"><span data-stu-id="cfab2-117">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="cfab2-118">Ключевое слово `val` определяет поле и его тип, но не разрешает выполнять инициализацию.</span><span class="sxs-lookup"><span data-stu-id="cfab2-118">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="cfab2-119">Вместо этого объявления `val` инициализируются с нулем или значением null.</span><span class="sxs-lookup"><span data-stu-id="cfab2-119">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="cfab2-120">Поэтому для структур с неявным конструктором (то есть параметрами, заданными непосредственно после имени структуры в объявлении) требуется, чтобы объявления `val` были помечены атрибутом `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="cfab2-120">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="cfab2-121">Структуры, имеющие определенный конструктор, по-прежнему поддерживают инициализацию с нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="cfab2-121">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="cfab2-122">Таким образом, атрибут `DefaultValue` является объявлением того, что для поля допускается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="cfab2-122">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="cfab2-123">Неявные конструкторы для структур не выполняют каких-либо действий, так как привязки `let` и `do` не разрешены для типа, однако переданные значения параметров неявного конструктора доступны в виде закрытых полей.</span><span class="sxs-lookup"><span data-stu-id="cfab2-123">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="cfab2-124">Явные конструкторы могут способствовать инициализации значений полей.</span><span class="sxs-lookup"><span data-stu-id="cfab2-124">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="cfab2-125">Структура, которая имеет явный конструктор, по-прежнему поддерживают инициализацию с нулевым значением. Тем не менее, в объявлениях `DefaultValue` не следует использовать атрибут `val`, поскольку он вступает в конфликт с явным конструктором.</span><span class="sxs-lookup"><span data-stu-id="cfab2-125">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="cfab2-126">Дополнительные сведения о `val` объявления, в разделе [явные поля: `val` ключевое слово](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="cfab2-126">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="cfab2-127">В структурах допускается использование атрибутов и модификаторов доступности, для которых действуют те же правила, что и для других типов.</span><span class="sxs-lookup"><span data-stu-id="cfab2-127">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="cfab2-128">Дополнительные сведения см. в разделе [атрибуты](attributes.md) и [управления доступом](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="cfab2-128">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="cfab2-129">В следующих примерах кода показаны определения структуры.</span><span class="sxs-lookup"><span data-stu-id="cfab2-129">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="cfab2-130">Структура записи и размеченные объединения</span><span class="sxs-lookup"><span data-stu-id="cfab2-130">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="cfab2-131">Начиная с версии 4.1 F #, может представлять [записей](records.md) и [размеченные объединения](discriminated-unions.md) как структуры с `[<Struct>]` атрибута.</span><span class="sxs-lookup"><span data-stu-id="cfab2-131">Starting with F# 4.1, you can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="cfab2-132">Каждой статье для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="cfab2-132">See each article to learn more.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cfab2-133">См. также</span><span class="sxs-lookup"><span data-stu-id="cfab2-133">See Also</span></span>
[<span data-ttu-id="cfab2-134">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="cfab2-134">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="cfab2-135">Классы</span><span class="sxs-lookup"><span data-stu-id="cfab2-135">Classes</span></span>](classes.md)

[<span data-ttu-id="cfab2-136">Записи</span><span class="sxs-lookup"><span data-stu-id="cfab2-136">Records</span></span>](records.md)

[<span data-ttu-id="cfab2-137">Члены</span><span class="sxs-lookup"><span data-stu-id="cfab2-137">Members</span></span>](members/index.md)
