---
title: Свойства (F#)
description: 'Дополнительные сведения о F # свойства, являющиеся членами, которые представляют значения, связанные с объектом.'
ms.date: 05/16/2016
ms.openlocfilehash: 7aa71b1801b44fedcb420b824078004c6c240dc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566166"
---
# <a name="properties"></a><span data-ttu-id="93a11-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="93a11-103">Properties</span></span>

<span data-ttu-id="93a11-104">*Свойства* , члены, представляющие собой значения, связанные с объектом.</span><span class="sxs-lookup"><span data-stu-id="93a11-104">*Properties* are members that represent values associated with an object.</span></span>


## <a name="syntax"></a><span data-ttu-id="93a11-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93a11-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="93a11-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="93a11-106">Remarks</span></span>
<span data-ttu-id="93a11-107">Свойства представляют» имеет «связь в объектно ориентированное программирование, представляющий данные, связанные с экземплярами объекта или для статических свойств с типом.</span><span class="sxs-lookup"><span data-stu-id="93a11-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="93a11-108">Можно объявить свойства двумя способами, в зависимости от того, требуется ли явно указать (также называемый резервным хранилищем) базовое значение для свойства или если вы хотите разрешить компилятора для автоматического создания резервного хранилища для вас.</span><span class="sxs-lookup"><span data-stu-id="93a11-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="93a11-109">Как правило если свойство имеет только Простая оболочка для значения или переменной следует использовать более явным образом, если свойство имеет нетривиальный реализацию и автоматическим способом.</span><span class="sxs-lookup"><span data-stu-id="93a11-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="93a11-110">Чтобы объявить свойство явно, используйте `member` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="93a11-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="93a11-111">Это декларативный синтаксис следуют синтаксис, определяющий `get` и `set` методов, тоже именуемый *методы доступа*.</span><span class="sxs-lookup"><span data-stu-id="93a11-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="93a11-112">Различные виды явного синтаксиса, показанного в разделе "синтаксис" используются для чтения и записи свойств только для чтения и только для записи.</span><span class="sxs-lookup"><span data-stu-id="93a11-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="93a11-113">Для свойства только для чтения, определяется только `get` метода; для свойства только для записи, определите только `set` метод.</span><span class="sxs-lookup"><span data-stu-id="93a11-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="93a11-114">Обратите внимание, что, когда свойство имеет и `get` и `set` доступа к свойствам альтернативный синтаксис позволяет указать атрибуты и модификаторы, которые различны для каждого метода доступа, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="93a11-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="93a11-115">Для свойств чтения и записи, которые оба имеют `get` и `set` метод, порядок `get` и `set` , могут быть отменены.</span><span class="sxs-lookup"><span data-stu-id="93a11-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="93a11-116">Кроме того, можно предоставить синтаксис, показанный для `get` только и синтаксис, показанный для `set` только вместо использования комбинированного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="93a11-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="93a11-117">Это упрощает закомментировать отдельно `get` или `set` метод, если что-то может потребоваться сделать это.</span><span class="sxs-lookup"><span data-stu-id="93a11-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="93a11-118">Это альтернатива использованию комбинированного синтаксиса показана в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="93a11-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="93a11-119">Закрытые значения данных для свойств, называются удержанием *резервными хранилищами*.</span><span class="sxs-lookup"><span data-stu-id="93a11-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="93a11-120">Чтобы компилятор автоматически создать резервное хранилище, используйте ключевые слова `member val`, пропущен идентификатор самого себя, а затем задать выражение для инициализации свойства.</span><span class="sxs-lookup"><span data-stu-id="93a11-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="93a11-121">Если свойство является изменяемым, включите `with get, set`.</span><span class="sxs-lookup"><span data-stu-id="93a11-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="93a11-122">Например следующий тип класса содержит два автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="93a11-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="93a11-123">`Property1` доступно только для чтения и инициализируется значением аргумента, предоставленного для первичного конструктора и `Property2` можно задать свойство инициализации на пустую строку:</span><span class="sxs-lookup"><span data-stu-id="93a11-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="93a11-124">Автоматически реализованные свойства являются частью инициализации типа, поэтому они должны быть включены до определения членов других так же, как `let` привязок и `do` привязок в определении типа.</span><span class="sxs-lookup"><span data-stu-id="93a11-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="93a11-125">Обратите внимание, что выражение, которое инициализирует автоматически реализуемое свойство вычисляются только при инициализации, а не каждый раз, чтобы обращение к свойству.</span><span class="sxs-lookup"><span data-stu-id="93a11-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="93a11-126">Это поведение отличается от поведения-точно реализованное свойство.</span><span class="sxs-lookup"><span data-stu-id="93a11-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="93a11-127">Что фактически означает, что код для инициализации этих свойств будет добавлен в конструктор класса.</span><span class="sxs-lookup"><span data-stu-id="93a11-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="93a11-128">Рассмотрим следующий код, который показывает это различие.</span><span class="sxs-lookup"><span data-stu-id="93a11-128">Consider the following code that shows this difference:</span></span>

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

<span data-ttu-id="93a11-129">**Вывод**</span><span class="sxs-lookup"><span data-stu-id="93a11-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="93a11-130">Результат выполнения предыдущего кода показывает, что значение AutoProperty не изменяется при вызывается многократно, тогда как ExplicitProperty изменяется каждый раз, когда он вызывается.</span><span class="sxs-lookup"><span data-stu-id="93a11-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="93a11-131">Этот пример демонстрирует для автоматически реализуемого свойства выражение не вычисляется каждый раз, как метод считывания для явного свойства.</span><span class="sxs-lookup"><span data-stu-id="93a11-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>


>[!WARNING]
<span data-ttu-id="93a11-132">Существуют некоторые библиотеки, такие как Entity Framework (`System.Data.Entity`), выполнить пользовательские операции в конструкторы базовых классов, которые не могут работать с инициализации автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="93a11-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="93a11-133">В таком случае попробуйте использовать явную свойства.</span><span class="sxs-lookup"><span data-stu-id="93a11-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="93a11-134">Свойства могут быть членами классов, структур, размеченные объединения, записи, интерфейсы и расширения типов и также могут определяться в выражениях объектов.</span><span class="sxs-lookup"><span data-stu-id="93a11-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="93a11-135">Атрибуты могут применяться к свойствам.</span><span class="sxs-lookup"><span data-stu-id="93a11-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="93a11-136">Чтобы применить атрибут к свойству, запишите атрибут на отдельной строке перед свойством.</span><span class="sxs-lookup"><span data-stu-id="93a11-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="93a11-137">Дополнительные сведения см. в разделе [Атрибуты](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="93a11-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="93a11-138">По умолчанию свойства являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="93a11-138">By default, properties are public.</span></span> <span data-ttu-id="93a11-139">Модификаторы доступности могут также применяться к свойствам.</span><span class="sxs-lookup"><span data-stu-id="93a11-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="93a11-140">Чтобы применить модификатор доступности, добавьте его непосредственно перед именем свойства, если он должен применяться к обоим `get` и `set` методов; добавьте его перед `get` и `set` ключевые слова, если другой уровень доступа требуется для каждого метода доступа.</span><span class="sxs-lookup"><span data-stu-id="93a11-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="93a11-141">*Модификатор доступа* может принимать одно из следующих действий: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="93a11-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="93a11-142">Дополнительные сведения см. в статье [Управление доступом](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="93a11-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="93a11-143">Реализации свойств выполняются каждый раз, когда к свойству.</span><span class="sxs-lookup"><span data-stu-id="93a11-143">Property implementations are executed each time a property is accessed.</span></span>


## <a name="static-and-instance-properties"></a><span data-ttu-id="93a11-144">Статические методы и свойства экземпляра</span><span class="sxs-lookup"><span data-stu-id="93a11-144">Static and Instance Properties</span></span>
<span data-ttu-id="93a11-145">Свойства могут быть статическими или свойства экземпляра.</span><span class="sxs-lookup"><span data-stu-id="93a11-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="93a11-146">Статические свойства могут вызываться без экземпляра и используются для значений, связанных с типом, а не с отдельными объектами.</span><span class="sxs-lookup"><span data-stu-id="93a11-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="93a11-147">Для статических свойств опустите идентификатор самого себя.</span><span class="sxs-lookup"><span data-stu-id="93a11-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="93a11-148">Для свойства экземпляра требуется идентификатор самого себя.</span><span class="sxs-lookup"><span data-stu-id="93a11-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="93a11-149">Следующее определение статического свойства основан на сценарии, в котором имеется статическое поле `myStaticValue` , резервным хранилищем для свойства.</span><span class="sxs-lookup"><span data-stu-id="93a11-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="93a11-150">Свойства могут также быть-массив, в этом случае они называются *индексированных свойств*.</span><span class="sxs-lookup"><span data-stu-id="93a11-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="93a11-151">Дополнительные сведения см. в разделе [индексированные свойства](indexed-properties.md).</span><span class="sxs-lookup"><span data-stu-id="93a11-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>


## <a name="type-annotation-for-properties"></a><span data-ttu-id="93a11-152">Аннотация типа для свойств</span><span class="sxs-lookup"><span data-stu-id="93a11-152">Type Annotation for Properties</span></span>
<span data-ttu-id="93a11-153">Во многих случаях компилятор имеет достаточно информации для определения типа свойства из типа резервного хранилища, но можно задать тип явно, добавив аннотацию типа.</span><span class="sxs-lookup"><span data-stu-id="93a11-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="93a11-154">С помощью свойства методы доступа set</span><span class="sxs-lookup"><span data-stu-id="93a11-154">Using Property set Accessors</span></span>
<span data-ttu-id="93a11-155">Можно задавать свойства, предоставляющие `set` методы доступа с помощью `<-` оператор.</span><span class="sxs-lookup"><span data-stu-id="93a11-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="93a11-156">Выходные данные выглядят **20**.</span><span class="sxs-lookup"><span data-stu-id="93a11-156">The output is **20**.</span></span>


## <a name="abstract-properties"></a><span data-ttu-id="93a11-157">Абстрактные свойства</span><span class="sxs-lookup"><span data-stu-id="93a11-157">Abstract Properties</span></span>
<span data-ttu-id="93a11-158">Свойства могут быть абстрактными.</span><span class="sxs-lookup"><span data-stu-id="93a11-158">Properties can be abstract.</span></span> <span data-ttu-id="93a11-159">Как и для методов, `abstract` просто означает, что виртуальный диспетчеризации, связанное со свойством.</span><span class="sxs-lookup"><span data-stu-id="93a11-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="93a11-160">Абстрактные свойства не может быть истинно абстрактными, то есть определение в том же классе.</span><span class="sxs-lookup"><span data-stu-id="93a11-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="93a11-161">Таким образом, класс, который содержит это свойство является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="93a11-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="93a11-162">Кроме того абстрактный может означать только свойство является виртуальным, что в этом случае определение должно находиться в том же классе.</span><span class="sxs-lookup"><span data-stu-id="93a11-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="93a11-163">Обратите внимание, что абстрактные свойства не должно быть закрытым, если один метод доступа является абстрактным, второй также должен быть абстрактным.</span><span class="sxs-lookup"><span data-stu-id="93a11-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="93a11-164">Дополнительные сведения об абстрактных классах см. в разделе [абстрактные классы](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="93a11-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="93a11-165">См. также</span><span class="sxs-lookup"><span data-stu-id="93a11-165">See Also</span></span>
[<span data-ttu-id="93a11-166">Члены</span><span class="sxs-lookup"><span data-stu-id="93a11-166">Members</span></span>](index.md)

[<span data-ttu-id="93a11-167">Методы</span><span class="sxs-lookup"><span data-stu-id="93a11-167">Methods</span></span>](methods.md)
