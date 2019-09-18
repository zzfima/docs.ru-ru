---
title: Записи
description: Сведения о F# том, как записи представляют простые статистические выражения именованных значений, при необходимости с элементами.
ms.date: 06/09/2019
ms.openlocfilehash: 1ba002407b1ccbcbceed32df8636fb860e89e3b6
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053931"
---
# <a name="records"></a><span data-ttu-id="0400c-103">Записи</span><span class="sxs-lookup"><span data-stu-id="0400c-103">Records</span></span>

<span data-ttu-id="0400c-104">Записи представляют собой простые агрегаты именованных значений, которые могут иметь элементы.</span><span class="sxs-lookup"><span data-stu-id="0400c-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="0400c-105">Они могут быть либо структурами, либо ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="0400c-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="0400c-106">По умолчанию они являются ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="0400c-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="0400c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0400c-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="0400c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0400c-108">Remarks</span></span>

<span data-ttu-id="0400c-109">В предыдущем синтаксисе *TypeName* — это имя типа записи, *Label1* и *ярлык2* — имена значений, называемые *метками*, а *Type1* и *тип2* — типы этих значений.</span><span class="sxs-lookup"><span data-stu-id="0400c-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="0400c-110">*member-list* — это необязательный список элементов для типа.</span><span class="sxs-lookup"><span data-stu-id="0400c-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="0400c-111">`[<Struct>]` Атрибут можно использовать для создания записи структуры, а не для записи, которая является ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="0400c-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="0400c-112">Ниже приведены некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="0400c-112">Following are some examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="0400c-113">Если каждая метка находится в отдельной строке, точка с запятой является необязательной.</span><span class="sxs-lookup"><span data-stu-id="0400c-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="0400c-114">Значения можно задавать в выражениях, называемых *выражениями записи*.</span><span class="sxs-lookup"><span data-stu-id="0400c-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="0400c-115">Компилятор выводит тип из используемых меток (если метки достаточно отличаются от других типов записей).</span><span class="sxs-lookup"><span data-stu-id="0400c-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="0400c-116">Фигурные скобки ({}) заключают выражение записи.</span><span class="sxs-lookup"><span data-stu-id="0400c-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="0400c-117">В следующем коде показано выражение записи, которое инициализирует запись с тремя элементами с плавающей запятой `x`с `y` метками и `z`.</span><span class="sxs-lookup"><span data-stu-id="0400c-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="0400c-118">Не используйте сокращенную форму, если возможно наличие другого типа, который также имеет одинаковые метки.</span><span class="sxs-lookup"><span data-stu-id="0400c-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="0400c-119">Метки последнего объявленного типа имеют приоритет над элементами ранее объявленного типа, поэтому в предыдущем примере `mypoint3D` выводится `Point3D`как.</span><span class="sxs-lookup"><span data-stu-id="0400c-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="0400c-120">Можно явно указать тип записи, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0400c-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="0400c-121">Методы могут быть определены для типов записей так же, как для типов классов.</span><span class="sxs-lookup"><span data-stu-id="0400c-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="0400c-122">Создание записей с помощью выражений записи</span><span class="sxs-lookup"><span data-stu-id="0400c-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="0400c-123">Можно инициализировать записи с помощью меток, определенных в записи.</span><span class="sxs-lookup"><span data-stu-id="0400c-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="0400c-124">Выражение, которое делает это, называется *выражением записи*.</span><span class="sxs-lookup"><span data-stu-id="0400c-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="0400c-125">Используйте фигурные скобки, чтобы заключить выражение записи и использовать точку с запятой в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="0400c-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="0400c-126">В следующем примере показано, как создать запись.</span><span class="sxs-lookup"><span data-stu-id="0400c-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="0400c-127">Точки с запятой после последнего поля в выражении записи и в определении типа являются необязательными независимо от того, все ли поля находятся в одной строке.</span><span class="sxs-lookup"><span data-stu-id="0400c-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="0400c-128">При создании записи необходимо указать значения для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="0400c-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="0400c-129">Нельзя ссылаться на значения других полей в выражении инициализации для любого поля.</span><span class="sxs-lookup"><span data-stu-id="0400c-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="0400c-130">В следующем коде тип `myRecord2` выводится из имен полей.</span><span class="sxs-lookup"><span data-stu-id="0400c-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="0400c-131">При необходимости можно явно указать имя типа.</span><span class="sxs-lookup"><span data-stu-id="0400c-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="0400c-132">Другая форма создания записи может быть полезной, если необходимо скопировать существующую запись и, возможно, изменить некоторые значения полей.</span><span class="sxs-lookup"><span data-stu-id="0400c-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="0400c-133">Это показано в следующей строке кода.</span><span class="sxs-lookup"><span data-stu-id="0400c-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="0400c-134">Эта форма выражения записи называется *выражением копирования и обновления записи*.</span><span class="sxs-lookup"><span data-stu-id="0400c-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="0400c-135">По умолчанию записи являются неизменяемыми; Однако вы можете легко создавать измененные записи с помощью выражения копирования и обновления.</span><span class="sxs-lookup"><span data-stu-id="0400c-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="0400c-136">Можно также явно указать изменяемое поле.</span><span class="sxs-lookup"><span data-stu-id="0400c-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="0400c-137">Не используйте атрибут DefaultValue с полями записей.</span><span class="sxs-lookup"><span data-stu-id="0400c-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="0400c-138">Лучшим подходом является определение экземпляров по умолчанию для записей с полями, которые инициализируются значениями по умолчанию, а затем использование выражения копирования и обновления записей для установки любых полей, которые отличаются от значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0400c-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

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

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="0400c-139">Создание взаимно рекурсивных записей</span><span class="sxs-lookup"><span data-stu-id="0400c-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="0400c-140">Иногда при создании записи может потребоваться, чтобы она зависела от другого типа, который вы хотите определить позже.</span><span class="sxs-lookup"><span data-stu-id="0400c-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="0400c-141">Это ошибка компиляции, если не определить типы записей для взаимной рекурсивной рекурсии.</span><span class="sxs-lookup"><span data-stu-id="0400c-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="0400c-142">Определение взаимно рекурсивных записей выполняется с помощью `and` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="0400c-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="0400c-143">Это позволяет связать 2 или более типов записей вместе.</span><span class="sxs-lookup"><span data-stu-id="0400c-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="0400c-144">Например, следующий код определяет `Person` тип и `Address` как взаимно рекурсивный:</span><span class="sxs-lookup"><span data-stu-id="0400c-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string
    Occupant: Person }
```

<span data-ttu-id="0400c-145">Если бы вы определили предыдущий пример без `and` ключевого слова, он не будет компилироваться.</span><span class="sxs-lookup"><span data-stu-id="0400c-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="0400c-146">Для взаимно рекурсивных определений требуется ключевоеслово.`and`</span><span class="sxs-lookup"><span data-stu-id="0400c-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="0400c-147">Сопоставление шаблонов с записями</span><span class="sxs-lookup"><span data-stu-id="0400c-147">Pattern Matching with Records</span></span>

<span data-ttu-id="0400c-148">Записи можно использовать с сопоставлением шаблонов.</span><span class="sxs-lookup"><span data-stu-id="0400c-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="0400c-149">Можно явно указать некоторые поля и предоставить переменные для других полей, которые будут назначаться при совпадении.</span><span class="sxs-lookup"><span data-stu-id="0400c-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="0400c-150">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0400c-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="0400c-151">Выходные данные этого кода выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0400c-151">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="0400c-152">Различия между записями и классами</span><span class="sxs-lookup"><span data-stu-id="0400c-152">Differences Between Records and Classes</span></span>

<span data-ttu-id="0400c-153">Поля записей отличаются от классов тем, что они автоматически предоставляются как свойства и используются при создании и копировании записей.</span><span class="sxs-lookup"><span data-stu-id="0400c-153">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="0400c-154">Построение записей также отличается от создания класса.</span><span class="sxs-lookup"><span data-stu-id="0400c-154">Record construction also differs from class construction.</span></span> <span data-ttu-id="0400c-155">В типе записи нельзя определить конструктор.</span><span class="sxs-lookup"><span data-stu-id="0400c-155">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="0400c-156">Вместо этого применяется синтаксис создания, описанный в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0400c-156">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="0400c-157">Классы не имеют прямой связи между параметрами конструктора, полями и свойствами.</span><span class="sxs-lookup"><span data-stu-id="0400c-157">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="0400c-158">Как и типы Union и Structure, записи имеют семантику структурного равенства.</span><span class="sxs-lookup"><span data-stu-id="0400c-158">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="0400c-159">Классы имеют семантику равенства ссылок.</span><span class="sxs-lookup"><span data-stu-id="0400c-159">Classes have reference equality semantics.</span></span> <span data-ttu-id="0400c-160">Это действие представлено в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="0400c-160">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="0400c-161">Результат выполнения этого кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0400c-161">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="0400c-162">Если написать тот же код с классами, то два объекта класса будут неравными, так как два значения будут представлять два объекта в куче и будут сравниваться только адреса (если только тип класса не переопределит `System.Object.Equals` метод).</span><span class="sxs-lookup"><span data-stu-id="0400c-162">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="0400c-163">Если для записей требуется равенство ссылок, добавьте атрибут `[<ReferenceEquality>]` над записью.</span><span class="sxs-lookup"><span data-stu-id="0400c-163">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="0400c-164">См. также</span><span class="sxs-lookup"><span data-stu-id="0400c-164">See also</span></span>

- [<span data-ttu-id="0400c-165">Типы языка F#</span><span class="sxs-lookup"><span data-stu-id="0400c-165">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="0400c-166">Классы</span><span class="sxs-lookup"><span data-stu-id="0400c-166">Classes</span></span>](classes.md)
- [<span data-ttu-id="0400c-167">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="0400c-167">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0400c-168">Равенство ссылок</span><span class="sxs-lookup"><span data-stu-id="0400c-168">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="0400c-169">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="0400c-169">Pattern Matching</span></span>](pattern-matching.md)
