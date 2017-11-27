---
title: "Явные поля. Ключевое слово val (F#)"
description: "Дополнительные сведения о F # «val» ключевое слово, которое используется для объявления расположения для сохранения значения в типе класса или структуры без инициализации типа."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3bdbc745-436b-407f-bf54-5d11ca829cd0
ms.openlocfilehash: cee53a48f08aec89b0bdd40189ed331cadee877d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="explicit-fields-the-val-keyword"></a><span data-ttu-id="21f76-104">Явные поля. Ключевое слово val</span><span class="sxs-lookup"><span data-stu-id="21f76-104">Explicit Fields: The val Keyword</span></span>

<span data-ttu-id="21f76-105">Ключевое слово `val` используется для объявления расположения для сохранения значения в типе класса или структуры без его инициализации.</span><span class="sxs-lookup"><span data-stu-id="21f76-105">The `val` keyword is used to declare a location to store a value in a class or structure type, without initializing it.</span></span> <span data-ttu-id="21f76-106">Места хранения, объявленные таким образом, называются *явные поля*.</span><span class="sxs-lookup"><span data-stu-id="21f76-106">Storage locations declared in this manner are called *explicit fields*.</span></span> <span data-ttu-id="21f76-107">Ключевое слово `val` можно также использовать вместе с ключевым словом `member` для объявления автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="21f76-107">Another use of the `val` keyword is in conjunction with the `member` keyword to declare an auto-implemented property.</span></span> <span data-ttu-id="21f76-108">Дополнительные сведения об автоматически реализуемых свойствах см. в разделе [свойства](properties.md).</span><span class="sxs-lookup"><span data-stu-id="21f76-108">For more information on auto-implemented properties, see [Properties](properties.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="21f76-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21f76-109">Syntax</span></span>

```fsharp
val [ mutable ] [ access-modifier ] field-name : type-name
```

## <a name="remarks"></a><span data-ttu-id="21f76-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="21f76-110">Remarks</span></span>
<span data-ttu-id="21f76-111">Обычно поля в типе класса или структуры задаются с помощью привязки `let`.</span><span class="sxs-lookup"><span data-stu-id="21f76-111">The usual way to define fields in a class or structure type is to use a `let` binding.</span></span> <span data-ttu-id="21f76-112">Однако привязки `let` должны инициализироваться как часть конструктора класса, что не всегда возможно, необходимо или желательно.</span><span class="sxs-lookup"><span data-stu-id="21f76-112">However, `let` bindings must be initialized as part of the class constructor, which is not always possible, necessary, or desirable.</span></span> <span data-ttu-id="21f76-113">Если требуется неинициализированное поле, можно использовать ключевое слово `val`.</span><span class="sxs-lookup"><span data-stu-id="21f76-113">You can use the `val` keyword when you want a field that is uninitialized.</span></span>

<span data-ttu-id="21f76-114">Явные поля могут быть статическими или не статическими.</span><span class="sxs-lookup"><span data-stu-id="21f76-114">Explicit fields can be static or non-static.</span></span> <span data-ttu-id="21f76-115">*Модификатор доступа* может быть `public`, `private`, или `internal`.</span><span class="sxs-lookup"><span data-stu-id="21f76-115">The *access-modifier* can be `public`, `private`, or `internal`.</span></span> <span data-ttu-id="21f76-116">По умолчанию явные поля являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="21f76-116">By default, explicit fields are public.</span></span> <span data-ttu-id="21f76-117">Это отличается от привязок `let` в классах, которые всегда являются закрытыми.</span><span class="sxs-lookup"><span data-stu-id="21f76-117">This differs from `let` bindings in classes, which are always private.</span></span>

<span data-ttu-id="21f76-118">[DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) атрибут необходим для явных полей в типах классов, имеющих первичный конструктор.</span><span class="sxs-lookup"><span data-stu-id="21f76-118">The [DefaultValue](https://msdn.microsoft.com/library/a3a3307b-8c05-441e-b109-245511614d58) attribute is required on explicit fields in class types that have a primary constructor.</span></span> <span data-ttu-id="21f76-119">Этот атрибут указывает, что поле инициализируется нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="21f76-119">This attribute specifies that the field is initialized to zero.</span></span> <span data-ttu-id="21f76-120">Тип поля должен поддерживать инициализацию нулем.</span><span class="sxs-lookup"><span data-stu-id="21f76-120">The type of the field must support zero-initialization.</span></span> <span data-ttu-id="21f76-121">Тип поддерживает инициализацию нулем, если он является одним из следующих типов.</span><span class="sxs-lookup"><span data-stu-id="21f76-121">A type supports zero-initialization if it is one of the following:</span></span>

- <span data-ttu-id="21f76-122">Тип-примитив, который имеет нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="21f76-122">A primitive type that has a zero value.</span></span>

- <span data-ttu-id="21f76-123">Тип, поддерживающий значение null как нормальное значение, как аномальное значение или как представление значения.</span><span class="sxs-lookup"><span data-stu-id="21f76-123">A type that supports a null value, either as a normal value, as an abnormal value, or as a representation of a value.</span></span> <span data-ttu-id="21f76-124">Сюда входят классы, кортежи, записи, функции, интерфейсы, ссылочные типы .NET, тип `unit` и типы размеченного объединения.</span><span class="sxs-lookup"><span data-stu-id="21f76-124">This includes classes, tuples, records, functions, interfaces, .NET reference types, the `unit` type, and discriminated union types.</span></span>

- <span data-ttu-id="21f76-125">Тип значения .NET.</span><span class="sxs-lookup"><span data-stu-id="21f76-125">A .NET value type.</span></span>

- <span data-ttu-id="21f76-126">Структура, все поля которой поддерживают нулевое значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="21f76-126">A structure whose fields all support a default zero value.</span></span>


<span data-ttu-id="21f76-127">Например, неизменяемое поле с именем `someField` имеет резервное поле в скомпилированном в .NET представлении с именем `someField@`, и вы обращаетесь к хранимому значению, используя свойство с именем `someField`.</span><span class="sxs-lookup"><span data-stu-id="21f76-127">For example, an immutable field called `someField` has a backing field in the .NET compiled representation with the name `someField@`, and you access the stored value using a property named `someField`.</span></span>

<span data-ttu-id="21f76-128">Для изменяемого поля скомпилированное в .NET представление является полем .NET.</span><span class="sxs-lookup"><span data-stu-id="21f76-128">For a mutable field, the .NET compiled representation is a .NET field.</span></span>


>[!WARNING] 
<span data-ttu-id="21f76-129">`Note`Пространство имен .NET Framework `System.ComponentModel` содержит атрибут с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="21f76-129">`Note` The .NET Framework namespace `System.ComponentModel` contains an attribute that has the same name.</span></span> <span data-ttu-id="21f76-130">Сведения об этом атрибуте см. в разделе `System.ComponentModel.DefaultValueAttribute`.</span><span class="sxs-lookup"><span data-stu-id="21f76-130">For information about this attribute, see `System.ComponentModel.DefaultValueAttribute`.</span></span>


<span data-ttu-id="21f76-131">В следующем коде показано использование явных полей и для сравнения привязки `let` в классе, имеющем первичный конструктор.</span><span class="sxs-lookup"><span data-stu-id="21f76-131">The following code shows the use of explicit fields and, for comparison, a `let` binding in a class that has a primary constructor.</span></span> <span data-ttu-id="21f76-132">Обратите внимание, что привязанное с помощью `let` поле `myInt1` является закрытым.</span><span class="sxs-lookup"><span data-stu-id="21f76-132">Note that the `let`-bound field `myInt1` is private.</span></span> <span data-ttu-id="21f76-133">Если на привязанное с помощью `let` поле `myInt1` существует ссылка из метода-члена, идентификатор самого поля `this` не требуется.</span><span class="sxs-lookup"><span data-stu-id="21f76-133">When the `let`-bound field `myInt1` is referenced from a member method, the self identifier `this` is not required.</span></span> <span data-ttu-id="21f76-134">Но если вы обращаетесь к явным полям `myInt2` и `myString`, идентификатор самого поля обязателен.</span><span class="sxs-lookup"><span data-stu-id="21f76-134">But when you are referencing the explicit fields `myInt2` and `myString`, the self identifier is required.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6701.fs)]

<span data-ttu-id="21f76-135">Выходные данные выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="21f76-135">The output is as follows:</span></span>

```
11 12 abc
30 def
```

<span data-ttu-id="21f76-136">В следующем коде показывается использование явных полей в классе, в котором нет первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="21f76-136">The following code shows the use of explicit fields in a class that does not have a primary constructor.</span></span> <span data-ttu-id="21f76-137">В этом случае атрибут `DefaultValue` не требуется, но все поля должны быть инициализированы в конструкторах, определенных для типа.</span><span class="sxs-lookup"><span data-stu-id="21f76-137">In this case, the `DefaultValue` attribute is not required, but all the fields must be initialized in the constructors that are defined for the type.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6702.fs)]

<span data-ttu-id="21f76-138">В результате получается `35 22`.</span><span class="sxs-lookup"><span data-stu-id="21f76-138">The output is `35 22`.</span></span>

<span data-ttu-id="21f76-139">В следующем коде демонстрируется использование явных полей в структуре.</span><span class="sxs-lookup"><span data-stu-id="21f76-139">The following code shows the use of explicit fields in a structure.</span></span> <span data-ttu-id="21f76-140">Так как структура является типом значения, она автоматически имеет конструктор по умолчанию, который задает для полей значение ноль.</span><span class="sxs-lookup"><span data-stu-id="21f76-140">Because a structure is a value type, it automatically has a default constructor that sets the values of its fields to zero.</span></span> <span data-ttu-id="21f76-141">Таким образом, атрибут `DefaultValue` не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="21f76-141">Therefore, the `DefaultValue` attribute is not required.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6703.fs)]

<span data-ttu-id="21f76-142">В результате получается `11 xyz`.</span><span class="sxs-lookup"><span data-stu-id="21f76-142">The output is `11 xyz`.</span></span>

<span data-ttu-id="21f76-143">Явные поля не предназначены для обычного использования.</span><span class="sxs-lookup"><span data-stu-id="21f76-143">Explicit fields are not intended for routine use.</span></span> <span data-ttu-id="21f76-144">Как правило, по возможности следует использовать привязку `let` в классе вместо явного поля.</span><span class="sxs-lookup"><span data-stu-id="21f76-144">In general, when possible you should use a `let` binding in a class instead of an explicit field.</span></span> <span data-ttu-id="21f76-145">Явные поля удобны в некоторых сценариях взаимодействия, например если необходимо определить структуру, которая будет использоваться в вызове платформой собственного API или в сценариях COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="21f76-145">Explicit fields are useful in certain interoperability scenarios, such as when you need to define a structure that will be used in a platform invoke call to a native API, or in COM interop scenarios.</span></span> <span data-ttu-id="21f76-146">Дополнительные сведения см. в разделе [внешние функции](../functions/external-functions.md).</span><span class="sxs-lookup"><span data-stu-id="21f76-146">For more information, see [External Functions](../functions/external-functions.md).</span></span> <span data-ttu-id="21f76-147">Кроме того, явное поле может потребоваться при работе с генератором кода F#, который порождает классы без первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="21f76-147">Another situation in which an explicit field might be necessary is when you are working with an F# code generator which emits classes without a primary constructor.</span></span> <span data-ttu-id="21f76-148">Явные поля также полезны для потокостатических переменных или подобных конструкций.</span><span class="sxs-lookup"><span data-stu-id="21f76-148">Explicit fields are also useful for thread-static variables or similar constructs.</span></span> <span data-ttu-id="21f76-149">Для получения дополнительной информации см. `System.ThreadStaticAttribute`.</span><span class="sxs-lookup"><span data-stu-id="21f76-149">For more information, see `System.ThreadStaticAttribute`.</span></span>

<span data-ttu-id="21f76-150">Если ключевые слова `member val` появляются вместе в определении типа, то это определение автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="21f76-150">When the keywords `member val` appear together in a type definition, it is a definition of an automatically implemented property.</span></span> <span data-ttu-id="21f76-151">Дополнительные сведения см. в разделе [свойства](properties.md).</span><span class="sxs-lookup"><span data-stu-id="21f76-151">For more information, see [Properties](properties.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="21f76-152">См. также</span><span class="sxs-lookup"><span data-stu-id="21f76-152">See Also</span></span>
[<span data-ttu-id="21f76-153">Свойства</span><span class="sxs-lookup"><span data-stu-id="21f76-153">Properties</span></span>](properties.md)

[<span data-ttu-id="21f76-154">Члены</span><span class="sxs-lookup"><span data-stu-id="21f76-154">Members</span></span>](index.md)

[<span data-ttu-id="21f76-155">Привязки `let` в классах</span><span class="sxs-lookup"><span data-stu-id="21f76-155">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
