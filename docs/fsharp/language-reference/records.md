---
title: "Записи (F#)"
description: "Узнайте, как записи F # представляют простые агрегаты именованных значений, Дополнительно с членами."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3a3701ea-4308-4fa1-9b5c-b955c470f17a
ms.openlocfilehash: 478ab74ad32cc6e53daffd1bd6229729149d2a1e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="records"></a><span data-ttu-id="83d12-104">Записи</span><span class="sxs-lookup"><span data-stu-id="83d12-104">Records</span></span>

<span data-ttu-id="83d12-105">Записи представляют собой простые агрегаты именованных значений, которые могут иметь элементы.</span><span class="sxs-lookup"><span data-stu-id="83d12-105">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="83d12-106">Начиная с версии 4.1 F #, они могут выступать структуры или ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="83d12-106">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="83d12-107">Они являются ссылочными типами, по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83d12-107">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="83d12-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83d12-108">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename = {
    [ mutable ] label1 : type1;
    [ mutable ] label2 : type2;
    ...
}
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="83d12-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="83d12-109">Remarks</span></span>
<span data-ttu-id="83d12-110">В предыдущем синтаксисе *typename* — имя типа записи *label1* и *label2* — это имена значений, называют *метки*, и *тип1* и *тип2* типы из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="83d12-110">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="83d12-111">*Список членов* — необязательный список членов для типа.</span><span class="sxs-lookup"><span data-stu-id="83d12-111">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="83d12-112">Можно использовать `[<Struct>]` атрибут для создания записи структуры, а не запись, которая является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="83d12-112">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="83d12-113">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="83d12-113">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="83d12-114">Когда каждая метка находится на отдельной строке, точка с запятой является необязательным.</span><span class="sxs-lookup"><span data-stu-id="83d12-114">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="83d12-115">Можно задать значения в выражениях, называемых *запись выражениях*.</span><span class="sxs-lookup"><span data-stu-id="83d12-115">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="83d12-116">Компилятор выводит тип из подписи (если метки в достаточной степени отличаются от других типов записи).</span><span class="sxs-lookup"><span data-stu-id="83d12-116">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="83d12-117">Фигурные скобки ({}) заключить выражение записи.</span><span class="sxs-lookup"><span data-stu-id="83d12-117">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="83d12-118">Ниже показано выражение записи, инициализирующее запись с тремя элементами с плавающей запятой с метками `x`, `y` и `z`.</span><span class="sxs-lookup"><span data-stu-id="83d12-118">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="83d12-119">Не используйте сокращенной форме, если может быть другого типа, в которой также совпадают с метками.</span><span class="sxs-lookup"><span data-stu-id="83d12-119">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="83d12-120">Метки последнего объявленного типа имеют приоритет над метками ранее объявленного типа, поэтому в предыдущем примере `mypoint3D` определяется как `Point3D`.</span><span class="sxs-lookup"><span data-stu-id="83d12-120">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="83d12-121">Можно явно указать тип записи, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="83d12-121">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="83d12-122">Методы могут определяться для типов записей, как и в случае типов класса.</span><span class="sxs-lookup"><span data-stu-id="83d12-122">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="83d12-123">Создание записей с помощью выражений записей</span><span class="sxs-lookup"><span data-stu-id="83d12-123">Creating Records by Using Record Expressions</span></span>
<span data-ttu-id="83d12-124">Записи можно инициализировать с помощью меток, которые определены в записи.</span><span class="sxs-lookup"><span data-stu-id="83d12-124">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="83d12-125">Выражение, которое делает это называется *записать выражение*.</span><span class="sxs-lookup"><span data-stu-id="83d12-125">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="83d12-126">Используйте фигурные скобки заключите выражения записи и используют в качестве разделителя точку с запятой.</span><span class="sxs-lookup"><span data-stu-id="83d12-126">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="83d12-127">В следующем примере показано, как создать запись.</span><span class="sxs-lookup"><span data-stu-id="83d12-127">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="83d12-128">Точка с запятой после последнего поля выражения записи и в определении типа являются необязательными, независимо от того, является ли поля находятся в одной строке.</span><span class="sxs-lookup"><span data-stu-id="83d12-128">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="83d12-129">При создании записи необходимо указать значения для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="83d12-129">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="83d12-130">Нельзя ссылаться на значения других полей в выражении инициализации для любого поля.</span><span class="sxs-lookup"><span data-stu-id="83d12-130">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="83d12-131">В следующем коде тип `myRecord2` определяется на основе имен полей.</span><span class="sxs-lookup"><span data-stu-id="83d12-131">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="83d12-132">При необходимости можно явно указать имя типа.</span><span class="sxs-lookup"><span data-stu-id="83d12-132">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="83d12-133">Другую форму конструкции записи можно использовать, когда необходимо скопировать существующую запись и при необходимости измените значения полей.</span><span class="sxs-lookup"><span data-stu-id="83d12-133">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="83d12-134">Это показано в следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="83d12-134">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="83d12-135">Эта форма выражения записи называется *копирование и обновление записей выражение*.</span><span class="sxs-lookup"><span data-stu-id="83d12-135">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="83d12-136">Записи являются неизменяемыми по умолчанию; Однако можно легко создать измененные записи с помощью копирования и обновить выражение.</span><span class="sxs-lookup"><span data-stu-id="83d12-136">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="83d12-137">Можно также явно указать изменяемого поля.</span><span class="sxs-lookup"><span data-stu-id="83d12-137">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="83d12-138">Не используйте атрибут DefaultValue с полями записи.</span><span class="sxs-lookup"><span data-stu-id="83d12-138">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="83d12-139">Лучшим подходом является определение экземпляров по умолчанию записи с полями, которые инициализируются значениями по умолчанию, а затем использовать копию и обновления выражения записи, чтобы установить все поля, которые отличаются от значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83d12-139">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
{
    field1 : int
    field2 : int
}

let defaultRecord1 = { field1 = 0; field2 = 0 }
let defaultRecord2 = { field1 = 1; field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with field2 = 42 }
```

## <a name="pattern-matching-with-records"></a><span data-ttu-id="83d12-140">Соответствие шаблону с записями</span><span class="sxs-lookup"><span data-stu-id="83d12-140">Pattern Matching with Records</span></span>
<span data-ttu-id="83d12-141">Записи можно использовать с сопоставлением шаблонов.</span><span class="sxs-lookup"><span data-stu-id="83d12-141">Records can be used with pattern matching.</span></span> <span data-ttu-id="83d12-142">Можно явно задать некоторые поля и указать переменные, значения для других полей, которые будут назначены при совпадении.</span><span class="sxs-lookup"><span data-stu-id="83d12-142">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="83d12-143">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="83d12-143">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="83d12-144">Результат выполнения этого кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="83d12-144">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="83d12-145">Различия между записями и классами</span><span class="sxs-lookup"><span data-stu-id="83d12-145">Differences Between Records and Classes</span></span>
<span data-ttu-id="83d12-146">Поля записей отличаются от классов в том, что они автоматически представляются как свойства, и они используются при создании и копировании записей.</span><span class="sxs-lookup"><span data-stu-id="83d12-146">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="83d12-147">Построение записей также отличается от создания класса.</span><span class="sxs-lookup"><span data-stu-id="83d12-147">Record construction also differs from class construction.</span></span> <span data-ttu-id="83d12-148">В типе записи нельзя определить конструктор.</span><span class="sxs-lookup"><span data-stu-id="83d12-148">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="83d12-149">Вместо этого применяется синтаксис конструкции, описанный в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="83d12-149">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="83d12-150">Классы не имеют прямых связей между параметрами конструктора, поля и свойства.</span><span class="sxs-lookup"><span data-stu-id="83d12-150">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="83d12-151">Как типы объединения и структуры записи обладают семантикой структурного равенства.</span><span class="sxs-lookup"><span data-stu-id="83d12-151">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="83d12-152">Классы имеют ссылки семантику равенства.</span><span class="sxs-lookup"><span data-stu-id="83d12-152">Classes have reference equality semantics.</span></span> <span data-ttu-id="83d12-153">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="83d12-153">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="83d12-154">При написании один и тот же код с классами, два объекта класса будут равны, так как два значения будут представлять два объекта в куче и будут сравниваться только адреса (если тип класса не переопределяет `System.Object.Equals` метода).</span><span class="sxs-lookup"><span data-stu-id="83d12-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="83d12-155">Если требуется сослаться равенства для записей, добавьте атрибут `[<ReferenceEquality>]` выше записи.</span><span class="sxs-lookup"><span data-stu-id="83d12-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="83d12-156">См. также</span><span class="sxs-lookup"><span data-stu-id="83d12-156">See Also</span></span>
[<span data-ttu-id="83d12-157">Типы языка F#</span><span class="sxs-lookup"><span data-stu-id="83d12-157">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="83d12-158">Классы</span><span class="sxs-lookup"><span data-stu-id="83d12-158">Classes</span></span>](classes.md)

[<span data-ttu-id="83d12-159">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="83d12-159">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="83d12-160">Равенство ссылок</span><span class="sxs-lookup"><span data-stu-id="83d12-160">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)

[<span data-ttu-id="83d12-161">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="83d12-161">Pattern Matching</span></span>](pattern-matching.md)
