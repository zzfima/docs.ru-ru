---
title: Записи (F#)
description: 'Узнайте, как записи F # представляют простые агрегаты именованных значений, Дополнительно с членами.'
ms.date: 05/16/2016
ms.openlocfilehash: ffb853ee11ff8cacb45dadf6ef14a4f29400aad4
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549611"
---
# <a name="records"></a><span data-ttu-id="be489-103">Записи</span><span class="sxs-lookup"><span data-stu-id="be489-103">Records</span></span>

<span data-ttu-id="be489-104">Записи представляют собой простые агрегаты именованных значений, которые могут иметь элементы.</span><span class="sxs-lookup"><span data-stu-id="be489-104">Records represent simple aggregates of named values, optionally with members.</span></span>  <span data-ttu-id="be489-105">Начиная с версии 4.1 F #, они могут выступать структуры или ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="be489-105">Starting with F# 4.1, they can either be structs or reference types.</span></span>  <span data-ttu-id="be489-106">Они являются ссылочными типами, по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="be489-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="be489-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be489-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="be489-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="be489-108">Remarks</span></span>

<span data-ttu-id="be489-109">В предыдущем синтаксисе *typename* — имя типа записи *label1* и *label2* — это имена значений, называют *метки*, и *тип1* и *тип2* типы из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="be489-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="be489-110">*Список членов* — необязательный список членов для типа.</span><span class="sxs-lookup"><span data-stu-id="be489-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="be489-111">Можно использовать `[<Struct>]` атрибут для создания записи структуры, а не запись, которая является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="be489-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="be489-112">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="be489-112">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="be489-113">Когда каждая метка находится на отдельной строке, точка с запятой является необязательным.</span><span class="sxs-lookup"><span data-stu-id="be489-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="be489-114">Можно задать значения в выражениях, называемых *запись выражениях*.</span><span class="sxs-lookup"><span data-stu-id="be489-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="be489-115">Компилятор выводит тип из подписи (если метки в достаточной степени отличаются от других типов записи).</span><span class="sxs-lookup"><span data-stu-id="be489-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="be489-116">Фигурные скобки ({}) заключить выражение записи.</span><span class="sxs-lookup"><span data-stu-id="be489-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="be489-117">Ниже показано выражение записи, инициализирующее запись с тремя элементами с плавающей запятой с метками `x`, `y` и `z`.</span><span class="sxs-lookup"><span data-stu-id="be489-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="be489-118">Не используйте сокращенной форме, если может быть другого типа, в которой также совпадают с метками.</span><span class="sxs-lookup"><span data-stu-id="be489-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="be489-119">Метки последнего объявленного типа имеют приоритет над метками ранее объявленного типа, поэтому в предыдущем примере `mypoint3D` определяется как `Point3D`.</span><span class="sxs-lookup"><span data-stu-id="be489-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="be489-120">Можно явно указать тип записи, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="be489-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="be489-121">Методы могут определяться для типов записей, как и в случае типов класса.</span><span class="sxs-lookup"><span data-stu-id="be489-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="be489-122">Создание записей с помощью выражений записей</span><span class="sxs-lookup"><span data-stu-id="be489-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="be489-123">Записи можно инициализировать с помощью меток, которые определены в записи.</span><span class="sxs-lookup"><span data-stu-id="be489-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="be489-124">Выражение, которое делает это называется *записать выражение*.</span><span class="sxs-lookup"><span data-stu-id="be489-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="be489-125">Используйте фигурные скобки заключите выражения записи и используют в качестве разделителя точку с запятой.</span><span class="sxs-lookup"><span data-stu-id="be489-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="be489-126">В следующем примере показано, как создать запись.</span><span class="sxs-lookup"><span data-stu-id="be489-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="be489-127">Точка с запятой после последнего поля выражения записи и в определении типа являются необязательными, независимо от того, является ли поля находятся в одной строке.</span><span class="sxs-lookup"><span data-stu-id="be489-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="be489-128">При создании записи необходимо указать значения для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="be489-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="be489-129">Нельзя ссылаться на значения других полей в выражении инициализации для любого поля.</span><span class="sxs-lookup"><span data-stu-id="be489-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="be489-130">В следующем коде тип `myRecord2` определяется на основе имен полей.</span><span class="sxs-lookup"><span data-stu-id="be489-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="be489-131">При необходимости можно явно указать имя типа.</span><span class="sxs-lookup"><span data-stu-id="be489-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="be489-132">Другую форму конструкции записи можно использовать, когда необходимо скопировать существующую запись и при необходимости измените значения полей.</span><span class="sxs-lookup"><span data-stu-id="be489-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="be489-133">Это показано в следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="be489-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="be489-134">Эта форма выражения записи называется *копирование и обновление записей выражение*.</span><span class="sxs-lookup"><span data-stu-id="be489-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="be489-135">Записи являются неизменяемыми по умолчанию; Однако можно легко создать измененные записи с помощью копирования и обновить выражение.</span><span class="sxs-lookup"><span data-stu-id="be489-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="be489-136">Можно также явно указать изменяемого поля.</span><span class="sxs-lookup"><span data-stu-id="be489-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="be489-137">Не используйте атрибут DefaultValue с полями записи.</span><span class="sxs-lookup"><span data-stu-id="be489-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="be489-138">Лучшим подходом является определение экземпляров по умолчанию записи с полями, которые инициализируются значениями по умолчанию, а затем использовать копию и обновления выражения записи, чтобы установить все поля, которые отличаются от значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="be489-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="pattern-matching-with-records"></a><span data-ttu-id="be489-139">Соответствие шаблону с записями</span><span class="sxs-lookup"><span data-stu-id="be489-139">Pattern Matching with Records</span></span>

<span data-ttu-id="be489-140">Записи можно использовать с сопоставлением шаблонов.</span><span class="sxs-lookup"><span data-stu-id="be489-140">Records can be used with pattern matching.</span></span> <span data-ttu-id="be489-141">Можно явно задать некоторые поля и указать переменные, значения для других полей, которые будут назначены при совпадении.</span><span class="sxs-lookup"><span data-stu-id="be489-141">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="be489-142">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="be489-142">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="be489-143">Результат выполнения этого кода выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="be489-143">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="be489-144">Различия между записями и классами</span><span class="sxs-lookup"><span data-stu-id="be489-144">Differences Between Records and Classes</span></span>

<span data-ttu-id="be489-145">Поля записей отличаются от классов в том, что они автоматически представляются как свойства, и они используются при создании и копировании записей.</span><span class="sxs-lookup"><span data-stu-id="be489-145">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="be489-146">Построение записей также отличается от создания класса.</span><span class="sxs-lookup"><span data-stu-id="be489-146">Record construction also differs from class construction.</span></span> <span data-ttu-id="be489-147">В типе записи нельзя определить конструктор.</span><span class="sxs-lookup"><span data-stu-id="be489-147">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="be489-148">Вместо этого применяется синтаксис конструкции, описанный в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="be489-148">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="be489-149">Классы не имеют прямых связей между параметрами конструктора, поля и свойства.</span><span class="sxs-lookup"><span data-stu-id="be489-149">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="be489-150">Как типы объединения и структуры записи обладают семантикой структурного равенства.</span><span class="sxs-lookup"><span data-stu-id="be489-150">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="be489-151">Классы имеют ссылки семантику равенства.</span><span class="sxs-lookup"><span data-stu-id="be489-151">Classes have reference equality semantics.</span></span> <span data-ttu-id="be489-152">Это действие представлено в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="be489-152">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="be489-153">Результат выполнения этого кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="be489-153">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="be489-154">При написании один и тот же код с классами, два объекта класса будут равны, так как два значения будут представлять два объекта в куче и будут сравниваться только адреса (если тип класса не переопределяет `System.Object.Equals` метода).</span><span class="sxs-lookup"><span data-stu-id="be489-154">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="be489-155">Если требуется сослаться равенства для записей, добавьте атрибут `[<ReferenceEquality>]` выше записи.</span><span class="sxs-lookup"><span data-stu-id="be489-155">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="be489-156">См. также</span><span class="sxs-lookup"><span data-stu-id="be489-156">See Also</span></span>

[<span data-ttu-id="be489-157">Типы языка F#</span><span class="sxs-lookup"><span data-stu-id="be489-157">F# Types</span></span>](fsharp-types.md)

[<span data-ttu-id="be489-158">Классы</span><span class="sxs-lookup"><span data-stu-id="be489-158">Classes</span></span>](classes.md)

[<span data-ttu-id="be489-159">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="be489-159">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="be489-160">Равенство ссылок</span><span class="sxs-lookup"><span data-stu-id="be489-160">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)

[<span data-ttu-id="be489-161">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="be489-161">Pattern Matching</span></span>](pattern-matching.md)
