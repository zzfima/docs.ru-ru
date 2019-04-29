---
title: Свойства
description: Дополнительные сведения о F# свойства, которые являются членами, которые представляют значения, связанные с объектом.
ms.date: 05/16/2016
ms.openlocfilehash: bf605ee1135bd3b3561bde9a8ae66353497931b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666369"
---
# <a name="properties"></a><span data-ttu-id="64015-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="64015-103">Properties</span></span>

<span data-ttu-id="64015-104">*Свойства* являются членами, которые представляют значения, связанные с объектом.</span><span class="sxs-lookup"><span data-stu-id="64015-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="64015-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64015-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="64015-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="64015-106">Remarks</span></span>

<span data-ttu-id="64015-107">Свойства представляют собой «имеет» связь в объектно ориентированное программирование, представляющий данные, связанные с экземплярами объекта, или для статических свойств, с типом.</span><span class="sxs-lookup"><span data-stu-id="64015-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="64015-108">Вы можете объявить свойства двумя способами, в зависимости от того, требуется ли явно указать базовое значение (также называется "резервным хранилищем") для свойства, или если вы хотите разрешить компилятору автоматически создавать резервное хранилище для вас.</span><span class="sxs-lookup"><span data-stu-id="64015-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="64015-109">Как правило если свойство имеет только это простая оболочка для значениям либо переменным следует использовать более явным образом, если свойство имеет нетривиальный реализацию и автоматическим способом.</span><span class="sxs-lookup"><span data-stu-id="64015-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="64015-110">Чтобы объявить свойство явно, используйте `member` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="64015-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="64015-111">Этот декларативный синтаксис сопровождается синтаксис, определяющий `get` и `set` методы, именуемый *методы доступа*.</span><span class="sxs-lookup"><span data-stu-id="64015-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="64015-112">Различные виды явного синтаксиса, показанного в разделе "синтаксис" используются для чтения и записи, только для чтения и только для записи свойств.</span><span class="sxs-lookup"><span data-stu-id="64015-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="64015-113">Для свойства только для чтения, можно определить только `get` метода; для свойства только для записи, определите только `set` метод.</span><span class="sxs-lookup"><span data-stu-id="64015-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="64015-114">Обратите внимание, что, когда свойство имеет оба `get` и `set` методы доступа, альтернативный синтаксис позволяет указать атрибуты и модификаторы доступа, которые различны для каждого метода доступа, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="64015-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="64015-115">Для свойства чтения/записи, которые имеют оба `get` и `set` метод, порядок `get` и `set` могли быть отменены.</span><span class="sxs-lookup"><span data-stu-id="64015-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="64015-116">Кроме того, можно указать синтаксис, показанный для `get` только и синтаксис, показанный для `set` только для того, вместо использования комбинированного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="64015-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="64015-117">Это облегчает закомментируйте отдельные `get` или `set` метод, если что-то может потребоваться сделать это.</span><span class="sxs-lookup"><span data-stu-id="64015-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="64015-118">В следующем коде показан этот альтернативный вариант для использования комбинированного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="64015-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="64015-119">Частные значения данных для свойств вызываются удержанием *резервными хранилищами*.</span><span class="sxs-lookup"><span data-stu-id="64015-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="64015-120">Способ применения компилятора автоматического создания резервного хранилища, используйте ключевые слова `member val`, пропущен идентификатор самого себя, а затем задать выражение для инициализации свойства.</span><span class="sxs-lookup"><span data-stu-id="64015-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="64015-121">Если свойство является изменяемым, включите `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="64015-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="64015-122">Например следующий тип класса включает два автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="64015-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="64015-123">`Property1` только для чтения и устанавливается равным аргумент, указанный для первичного конструктора, и `Property2` является настраиваемым свойством инициализации пустую строку:</span><span class="sxs-lookup"><span data-stu-id="64015-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="64015-124">Автоматически реализованные свойства являются частью инициализации типа, поэтому их необходимо включить перед другими определения членов, так же, как `let` привязок и `do` привязки в определении типа.</span><span class="sxs-lookup"><span data-stu-id="64015-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="64015-125">Обратите внимание на то, что выражение для инициализации автоматически реализуемого свойства вычисляется только при инициализации, а не при каждом обращении к свойству.</span><span class="sxs-lookup"><span data-stu-id="64015-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="64015-126">Это поведение отличается от поведения явно реализованные свойства.</span><span class="sxs-lookup"><span data-stu-id="64015-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="64015-127">Что фактически означает, что код для инициализации этих свойств добавляется в конструктор класса.</span><span class="sxs-lookup"><span data-stu-id="64015-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="64015-128">Рассмотрим следующий код, который показывает это различие:</span><span class="sxs-lookup"><span data-stu-id="64015-128">Consider the following code that shows this difference:</span></span>

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

<span data-ttu-id="64015-129">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="64015-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="64015-130">Выходные данные приведенного выше кода показывают, что значение AutoProperty остается неизменным при вызове многократно, тогда как ExplicitProperty изменяется каждый раз, когда он вызывается.</span><span class="sxs-lookup"><span data-stu-id="64015-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="64015-131">Это показывает, что для автоматически реализуемого свойства выражение не вычисляется каждый раз, как метод получения явные свойства.</span><span class="sxs-lookup"><span data-stu-id="64015-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="64015-132">Существуют некоторые библиотеки, такие как Entity Framework (`System.Data.Entity`), которые выполняют пользовательских операций в конструкторы базовых классов, которые не подходят для инициализации автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="64015-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="64015-133">В таком случае попробуйте использовать явные свойства.</span><span class="sxs-lookup"><span data-stu-id="64015-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="64015-134">Свойства могут быть членами классов, структур, размеченные объединения, записи, интерфейсы и расширения типов и также могут определяться в выражениях объектов.</span><span class="sxs-lookup"><span data-stu-id="64015-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="64015-135">Атрибуты могут быть применены к свойствам.</span><span class="sxs-lookup"><span data-stu-id="64015-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="64015-136">Чтобы применить атрибут к свойству, записи данного атрибута в отдельной строке перед свойством.</span><span class="sxs-lookup"><span data-stu-id="64015-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="64015-137">Дополнительные сведения см. в разделе [Атрибуты](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="64015-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="64015-138">По умолчанию свойства являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="64015-138">By default, properties are public.</span></span> <span data-ttu-id="64015-139">Модификаторы доступа могут также применяться к свойствам.</span><span class="sxs-lookup"><span data-stu-id="64015-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="64015-140">Чтобы применить модификатор доступности, добавьте его непосредственно перед именем свойства, если он предназначен для применяются к обеим версиям `get` и `set` методов; добавьте его перед `get` и `set` ключевые слова, если разные уровни доступа является обязательным для каждого метода доступа.</span><span class="sxs-lookup"><span data-stu-id="64015-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="64015-141">*Модификатор доступа* может принимать одно из следующих: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="64015-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="64015-142">Дополнительные сведения см. в статье [Управление доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="64015-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="64015-143">Реализации свойств выполняются каждый раз при обращении к свойству.</span><span class="sxs-lookup"><span data-stu-id="64015-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="64015-144">Статические и свойств экземпляра</span><span class="sxs-lookup"><span data-stu-id="64015-144">Static and Instance Properties</span></span>

<span data-ttu-id="64015-145">Свойства могут быть статическими или свойств экземпляра.</span><span class="sxs-lookup"><span data-stu-id="64015-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="64015-146">Статические свойства могут вызываться без экземпляра и используются для значений, связанный с типом, а не с отдельными объектами.</span><span class="sxs-lookup"><span data-stu-id="64015-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="64015-147">Для статических свойств опустите идентификатор самого себя.</span><span class="sxs-lookup"><span data-stu-id="64015-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="64015-148">Идентификатор самого себя является обязательным для свойств экземпляра.</span><span class="sxs-lookup"><span data-stu-id="64015-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="64015-149">Следующее определение статического свойства основан на сценарии, в котором имеется статическое поле `myStaticValue` то есть резервное хранилище для свойства.</span><span class="sxs-lookup"><span data-stu-id="64015-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="64015-150">Свойства могут также быть-массив, в этом случае они называются *индексированных свойств*.</span><span class="sxs-lookup"><span data-stu-id="64015-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="64015-151">Дополнительные сведения см. в разделе [индексированные свойства](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="64015-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="64015-152">Заметка типа для свойства</span><span class="sxs-lookup"><span data-stu-id="64015-152">Type Annotation for Properties</span></span>

<span data-ttu-id="64015-153">Во многих случаях компилятор получает достаточные сведения для определения типа свойства из типа резервного хранилища, но можно задать тип явно, добавив аннотацию типа.</span><span class="sxs-lookup"><span data-stu-id="64015-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="64015-154">С помощью свойства методы доступа set</span><span class="sxs-lookup"><span data-stu-id="64015-154">Using Property set Accessors</span></span>

<span data-ttu-id="64015-155">Можно задать свойства, которые предоставляют `set` методы доступа с помощью `<-` оператор.</span><span class="sxs-lookup"><span data-stu-id="64015-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="64015-156">Выходные данные **20**.</span><span class="sxs-lookup"><span data-stu-id="64015-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="64015-157">Абстрактные свойства</span><span class="sxs-lookup"><span data-stu-id="64015-157">Abstract Properties</span></span>

<span data-ttu-id="64015-158">Свойства могут быть абстрактными.</span><span class="sxs-lookup"><span data-stu-id="64015-158">Properties can be abstract.</span></span> <span data-ttu-id="64015-159">Как и в случае с методами, `abstract` просто означает, что виртуальной диспетчеризации, связанное со свойством.</span><span class="sxs-lookup"><span data-stu-id="64015-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="64015-160">Абстрактные свойства могут быть по-настоящему абстрактными, то есть без определения в том же классе.</span><span class="sxs-lookup"><span data-stu-id="64015-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="64015-161">Таким образом, класс, который содержит такое свойство является абстрактным классом.</span><span class="sxs-lookup"><span data-stu-id="64015-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="64015-162">Кроме того абстрактный просто может означать свойство является виртуальным, что в этом случае определение должно находиться в том же классе.</span><span class="sxs-lookup"><span data-stu-id="64015-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="64015-163">Обратите внимание, что абстрактные свойства не должны быть закрытыми, а если один метод доступа является абстрактным, второй также должен быть абстрактным.</span><span class="sxs-lookup"><span data-stu-id="64015-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="64015-164">Дополнительные сведения об абстрактных классах см. в разделе [абстрактные классы](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="64015-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="64015-165">См. также</span><span class="sxs-lookup"><span data-stu-id="64015-165">See also</span></span>

- [<span data-ttu-id="64015-166">Члены</span><span class="sxs-lookup"><span data-stu-id="64015-166">Members</span></span>](index.md)
- [<span data-ttu-id="64015-167">Методы</span><span class="sxs-lookup"><span data-stu-id="64015-167">Methods</span></span>](methods.md)
