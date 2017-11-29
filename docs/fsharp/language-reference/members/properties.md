---
title: "Свойства (F#)"
description: "Дополнительные сведения о F # свойства, являющиеся членами, которые представляют значения, связанные с объектом."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 98b363a5-ee6a-4b7b-b8ae-b244f2a0b316
ms.openlocfilehash: 53b93b20310c557ad9c30226bc08f85cbf2f3010
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="properties"></a><span data-ttu-id="a1b32-104">Свойства</span><span class="sxs-lookup"><span data-stu-id="a1b32-104">Properties</span></span>

<span data-ttu-id="a1b32-105">*Свойства* , члены, представляющие собой значения, связанные с объектом.</span><span class="sxs-lookup"><span data-stu-id="a1b32-105">*Properties* are members that represent values associated with an object.</span></span>


## <a name="syntax"></a><span data-ttu-id="a1b32-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1b32-106">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="a1b32-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a1b32-107">Remarks</span></span>
<span data-ttu-id="a1b32-108">Свойства представляют» имеет «связь в объектно ориентированное программирование, представляющий данные, связанные с экземплярами объекта или для статических свойств с типом.</span><span class="sxs-lookup"><span data-stu-id="a1b32-108">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="a1b32-109">Можно объявить свойства двумя способами, в зависимости от того, требуется ли явно указать (также называемый резервным хранилищем) базовое значение для свойства или если вы хотите разрешить компилятора для автоматического создания резервного хранилища для вас.</span><span class="sxs-lookup"><span data-stu-id="a1b32-109">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="a1b32-110">Как правило если свойство имеет только Простая оболочка для значения или переменной следует использовать более явным образом, если свойство имеет нетривиальный реализацию и автоматическим способом.</span><span class="sxs-lookup"><span data-stu-id="a1b32-110">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="a1b32-111">Чтобы объявить свойство явно, используйте `member` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="a1b32-111">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="a1b32-112">Это декларативный синтаксис следуют синтаксис, определяющий `get` и `set` методов, тоже именуемый *методы доступа*.</span><span class="sxs-lookup"><span data-stu-id="a1b32-112">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="a1b32-113">Различные виды явного синтаксиса, показанного в разделе "синтаксис" используются для чтения и записи свойств только для чтения и только для записи.</span><span class="sxs-lookup"><span data-stu-id="a1b32-113">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="a1b32-114">Для свойства только для чтения, определяется только `get` метода; для свойства только для записи, определите только `set` метод.</span><span class="sxs-lookup"><span data-stu-id="a1b32-114">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="a1b32-115">Обратите внимание, что, когда свойство имеет и `get` и `set` доступа к свойствам альтернативный синтаксис позволяет указать атрибуты и модификаторы, которые различны для каждого метода доступа, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="a1b32-115">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="a1b32-116">Для свойств чтения и записи, которые оба имеют `get` и `set` метод, порядок `get` и `set` , могут быть отменены.</span><span class="sxs-lookup"><span data-stu-id="a1b32-116">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="a1b32-117">Кроме того, можно предоставить синтаксис, показанный для `get` только и синтаксис, показанный для `set` только вместо использования комбинированного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="a1b32-117">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="a1b32-118">Это упрощает закомментировать отдельно `get` или `set` метод, если что-то может потребоваться сделать это.</span><span class="sxs-lookup"><span data-stu-id="a1b32-118">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="a1b32-119">Это альтернатива использованию комбинированного синтаксиса показана в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="a1b32-119">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="a1b32-120">Закрытые значения данных для свойств, называются удержанием *резервными хранилищами*.</span><span class="sxs-lookup"><span data-stu-id="a1b32-120">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="a1b32-121">Чтобы компилятор автоматически создать резервное хранилище, используйте ключевые слова `member val`, пропущен идентификатор самого себя, а затем задать выражение для инициализации свойства.</span><span class="sxs-lookup"><span data-stu-id="a1b32-121">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="a1b32-122">Если свойство является изменяемым, включите `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="a1b32-122">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="a1b32-123">Например следующий тип класса содержит два автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="a1b32-123">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="a1b32-124">`Property1`доступно только для чтения и инициализируется значением аргумента, предоставленного для первичного конструктора и `Property2` можно задать свойство инициализации на пустую строку:</span><span class="sxs-lookup"><span data-stu-id="a1b32-124">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="a1b32-125">Автоматически реализованные свойства являются частью инициализации типа, поэтому они должны быть включены до определения членов других так же, как `let` привязок и `do` привязок в определении типа.</span><span class="sxs-lookup"><span data-stu-id="a1b32-125">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="a1b32-126">Обратите внимание, что выражение, которое инициализирует автоматически реализуемое свойство вычисляются только при инициализации, а не каждый раз, чтобы обращение к свойству.</span><span class="sxs-lookup"><span data-stu-id="a1b32-126">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="a1b32-127">Это поведение отличается от поведения-точно реализованное свойство.</span><span class="sxs-lookup"><span data-stu-id="a1b32-127">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="a1b32-128">Что фактически означает, что код для инициализации этих свойств будет добавлен в конструктор класса.</span><span class="sxs-lookup"><span data-stu-id="a1b32-128">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="a1b32-129">Рассмотрим следующий код, который показывает это различие.</span><span class="sxs-lookup"><span data-stu-id="a1b32-129">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="a1b32-130">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="a1b32-130">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="a1b32-131">Результат выполнения предыдущего кода показывает, что значение AutoProperty не изменяется при вызывается многократно, тогда как ExplicitProperty изменяется каждый раз, когда он вызывается.</span><span class="sxs-lookup"><span data-stu-id="a1b32-131">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="a1b32-132">Этот пример демонстрирует для автоматически реализуемого свойства выражение не вычисляется каждый раз, как метод считывания для явного свойства.</span><span class="sxs-lookup"><span data-stu-id="a1b32-132">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>


>[!WARNING]
<span data-ttu-id="a1b32-133">Существуют некоторые библиотеки, такие как Entity Framework (`System.Data.Entity`), выполнить пользовательские операции в конструкторы базовых классов, которые не могут работать с инициализации автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="a1b32-133">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="a1b32-134">В таком случае попробуйте использовать явную свойства.</span><span class="sxs-lookup"><span data-stu-id="a1b32-134">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="a1b32-135">Свойства могут быть членами классов, структур, размеченные объединения, записи, интерфейсы и расширения типов и также могут определяться в выражениях объектов.</span><span class="sxs-lookup"><span data-stu-id="a1b32-135">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="a1b32-136">Атрибуты могут применяться к свойствам.</span><span class="sxs-lookup"><span data-stu-id="a1b32-136">Attributes can be applied to properties.</span></span> <span data-ttu-id="a1b32-137">Чтобы применить атрибут к свойству, запишите атрибут на отдельной строке перед свойством.</span><span class="sxs-lookup"><span data-stu-id="a1b32-137">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="a1b32-138">Дополнительные сведения см. в разделе [Атрибуты](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="a1b32-138">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="a1b32-139">По умолчанию свойства являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="a1b32-139">By default, properties are public.</span></span> <span data-ttu-id="a1b32-140">Модификаторы доступности могут также применяться к свойствам.</span><span class="sxs-lookup"><span data-stu-id="a1b32-140">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="a1b32-141">Чтобы применить модификатор доступности, добавьте его непосредственно перед именем свойства, если он должен применяться к обоим `get` и `set` методов; добавьте его перед `get` и `set` ключевые слова, если другой уровень доступа требуется для каждого метода доступа.</span><span class="sxs-lookup"><span data-stu-id="a1b32-141">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="a1b32-142">*Модификатор доступа* может принимать одно из следующих действий: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="a1b32-142">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="a1b32-143">Дополнительные сведения см. в статье [Управление доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="a1b32-143">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="a1b32-144">Реализации свойств выполняются каждый раз, когда к свойству.</span><span class="sxs-lookup"><span data-stu-id="a1b32-144">Property implementations are executed each time a property is accessed.</span></span>


## <a name="static-and-instance-properties"></a><span data-ttu-id="a1b32-145">Статические методы и свойства экземпляра</span><span class="sxs-lookup"><span data-stu-id="a1b32-145">Static and Instance Properties</span></span>
<span data-ttu-id="a1b32-146">Свойства могут быть статическими или свойства экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a1b32-146">Properties can be static or instance properties.</span></span> <span data-ttu-id="a1b32-147">Статические свойства могут вызываться без экземпляра и используются для значений, связанных с типом, а не с отдельными объектами.</span><span class="sxs-lookup"><span data-stu-id="a1b32-147">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="a1b32-148">Для статических свойств опустите идентификатор самого себя.</span><span class="sxs-lookup"><span data-stu-id="a1b32-148">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="a1b32-149">Для свойства экземпляра требуется идентификатор самого себя.</span><span class="sxs-lookup"><span data-stu-id="a1b32-149">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="a1b32-150">Следующее определение статического свойства основан на сценарии, в котором имеется статическое поле `myStaticValue` , резервным хранилищем для свойства.</span><span class="sxs-lookup"><span data-stu-id="a1b32-150">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="a1b32-151">Свойства могут также быть-массив, в этом случае они называются *индексированных свойств*.</span><span class="sxs-lookup"><span data-stu-id="a1b32-151">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="a1b32-152">Дополнительные сведения см. в разделе [индексированные свойства](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a1b32-152">For more information, see [Indexed Properties](indexed-properties.md).</span></span>


## <a name="type-annotation-for-properties"></a><span data-ttu-id="a1b32-153">Аннотация типа для свойств</span><span class="sxs-lookup"><span data-stu-id="a1b32-153">Type Annotation for Properties</span></span>
<span data-ttu-id="a1b32-154">Во многих случаях компилятор имеет достаточно информации для определения типа свойства из типа резервного хранилища, но можно задать тип явно, добавив аннотацию типа.</span><span class="sxs-lookup"><span data-stu-id="a1b32-154">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="a1b32-155">С помощью свойства методы доступа set</span><span class="sxs-lookup"><span data-stu-id="a1b32-155">Using Property set Accessors</span></span>
<span data-ttu-id="a1b32-156">Можно задавать свойства, предоставляющие `set` методы доступа с помощью `<-` оператор.</span><span class="sxs-lookup"><span data-stu-id="a1b32-156">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="a1b32-157">Выходные данные выглядят **20**.</span><span class="sxs-lookup"><span data-stu-id="a1b32-157">The output is **20**.</span></span>


## <a name="abstract-properties"></a><span data-ttu-id="a1b32-158">Абстрактные свойства</span><span class="sxs-lookup"><span data-stu-id="a1b32-158">Abstract Properties</span></span>
<span data-ttu-id="a1b32-159">Свойства могут быть абстрактными.</span><span class="sxs-lookup"><span data-stu-id="a1b32-159">Properties can be abstract.</span></span> <span data-ttu-id="a1b32-160">Как и для методов, `abstract` просто означает, что виртуальный диспетчеризации, связанное со свойством.</span><span class="sxs-lookup"><span data-stu-id="a1b32-160">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="a1b32-161">Абстрактные свойства не может быть истинно абстрактными, то есть определение в том же классе.</span><span class="sxs-lookup"><span data-stu-id="a1b32-161">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="a1b32-162">Таким образом, класс, который содержит это свойство является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="a1b32-162">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="a1b32-163">Кроме того абстрактный может означать только свойство является виртуальным, что в этом случае определение должно находиться в том же классе.</span><span class="sxs-lookup"><span data-stu-id="a1b32-163">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="a1b32-164">Обратите внимание, что абстрактные свойства не должно быть закрытым, если один метод доступа является абстрактным, второй также должен быть абстрактным.</span><span class="sxs-lookup"><span data-stu-id="a1b32-164">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="a1b32-165">Дополнительные сведения об абстрактных классах см. в разделе [абстрактные классы](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="a1b32-165">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="a1b32-166">См. также</span><span class="sxs-lookup"><span data-stu-id="a1b32-166">See Also</span></span>
[<span data-ttu-id="a1b32-167">Члены</span><span class="sxs-lookup"><span data-stu-id="a1b32-167">Members</span></span>](index.md)

[<span data-ttu-id="a1b32-168">Методы</span><span class="sxs-lookup"><span data-stu-id="a1b32-168">Methods</span></span>](methods.md)
