---
title: Конструкторы (F#)
description: 'Узнайте, как определить и использовать конструкторы в языке F # для создания и инициализации объектов классов и структур.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: d9062ae747c37bdc14104658ad0ec7d11f5545f0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="constructors"></a><span data-ttu-id="6b2a5-103">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="6b2a5-103">Constructors</span></span>

<span data-ttu-id="6b2a5-104">В этом разделе описывается определение и использование конструкторов для создания и инициализации объектов классов и структур.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>


## <a name="construction-of-class-objects"></a><span data-ttu-id="6b2a5-105">Создание объектов классов</span><span class="sxs-lookup"><span data-stu-id="6b2a5-105">Construction of Class Objects</span></span>
<span data-ttu-id="6b2a5-106">Объекты типов классов имеют конструкторы.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-106">Objects of class types have constructors.</span></span> <span data-ttu-id="6b2a5-107">Существует два типа конструкторов.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-107">There are two kinds of constructors.</span></span> <span data-ttu-id="6b2a5-108">Он первичного конструктора, параметры которого отображаются в круглых скобках после имени типа.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="6b2a5-109">Второй — необязательные дополнительные конструкторы, которые задаются с помощью `new` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="6b2a5-110">Такие дополнительные конструкторы необходимо вызвать первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="6b2a5-111">Главный конструктор содержит `let` и `do` привязок, которые записываются в начале определения класса.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="6b2a5-112">Объект `let` привязки объявляет закрытые поля и методы класса; `do` код выполняется привязка.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="6b2a5-113">Дополнительные сведения о `let` . в разделе привязок в конструкторах классов [ `let` привязок в классах](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6b2a5-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="6b2a5-114">Дополнительные сведения о `do` . в разделе привязок в конструкторах, [ `do` привязок в классах](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6b2a5-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="6b2a5-115">Независимо от того, необходимо вызвать конструктор основной или дополнительный, можно создать объекты с помощью `new` выражение с или без необязательный `new` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="6b2a5-116">Инициализация объектов вместе с аргументами конструктора либо путем перечисления аргументов в порядке и разделены запятыми и заключены в круглые скобки, или с помощью именованных аргументов и значений в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="6b2a5-117">Вы можно также задать свойства объекта во время создания объекта, используя имена свойств и присвоение значений, как можно использовать именованные аргументы конструктора.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="6b2a5-118">Следующий код иллюстрирует классом, имеющим различные способы создания объектов и конструктора.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="6b2a5-119">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="6b2a5-120">Создание структур</span><span class="sxs-lookup"><span data-stu-id="6b2a5-120">Construction of Structures</span></span>
<span data-ttu-id="6b2a5-121">Структуры имеют все правила классов.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="6b2a5-122">Таким образом, может иметь первичный конструктор, и можно задать дополнительные конструкторы с помощью `new`.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="6b2a5-123">Однако есть одно важное отличие между структурами и классами: структуры могут иметь конструктор по умолчанию (то есть без аргументов), даже если определена без первичного конструктора.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-123">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="6b2a5-124">Конструктор по умолчанию инициализирует все поля к значению по умолчанию для этого типа, обычно ноль или его эквивалент.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-124">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="6b2a5-125">Все конструкторы, которые задаются для структуры должны иметь по крайней мере один аргумент, чтобы они не конфликтовали с конструктором по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="6b2a5-126">Кроме того, структуры часто имеют поля, создаваемые с помощью `val` ключевого слова; классы также могут иметь эти поля.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="6b2a5-127">Структуры и классы, имеющие поля, определенные с помощью `val` ключевое слово могут также инициализироваться в дополнительных конструкторах с помощью выражений записей, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="6b2a5-128">Дополнительные сведения см. в разделе [явные поля: `val` ключевое слово](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="6b2a5-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>


## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="6b2a5-129">Выполнение побочных эффектов в конструкторах</span><span class="sxs-lookup"><span data-stu-id="6b2a5-129">Executing Side Effects in Constructors</span></span>
<span data-ttu-id="6b2a5-130">Главный конструктор в классе может выполнять код в `do` привязки.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="6b2a5-131">Однако, что делать, если необходимо выполнить код в дополнительном конструкторе без `do` привязки?</span><span class="sxs-lookup"><span data-stu-id="6b2a5-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="6b2a5-132">Чтобы сделать это, используйте `then` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="6b2a5-133">Побочные эффекты главного конструктора по-прежнему выполняются.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="6b2a5-134">Таким образом выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="6b2a5-135">Собственные идентификаторы в конструкторах</span><span class="sxs-lookup"><span data-stu-id="6b2a5-135">Self Identifiers in Constructors</span></span>
<span data-ttu-id="6b2a5-136">В других членов укажите имя для текущего объекта в определении каждого члена.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="6b2a5-137">Также можно поместить собственный идентификатор в первой строке определения класса с помощью `as` ключевое слово сразу после параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="6b2a5-138">Следующий пример иллюстрирует этот синтаксис.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="6b2a5-139">В дополнительных конструкторах также можно определить собственный идентификатор, поместив `as` предложение сразу же после параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="6b2a5-140">Следующий пример иллюстрирует этот синтаксис.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="6b2a5-141">При попытке использовать объект, пока она полностью определена, могут возникнуть проблемы.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="6b2a5-142">Таким образом использует собственный идентификатор может привести к компилятору выдавать предупреждение, а также вставлять дополнительные проверки, чтобы убедиться, что отсутствие обращения к членам объекта до инициализации объекта.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="6b2a5-143">Следует использовать только собственный идентификатор в `do` привязки первичного конструктора или после `then` ключевое слово в дополнительных конструкторов.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="6b2a5-144">Имя данного идентификатора не обязательно `this`.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="6b2a5-145">Это может быть любой допустимый идентификатор.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-145">It can be any valid identifier.</span></span>


## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="6b2a5-146">Присвоение значений свойствам при инициализации</span><span class="sxs-lookup"><span data-stu-id="6b2a5-146">Assigning Values to Properties at Initialization</span></span>
<span data-ttu-id="6b2a5-147">Можно присваивать значения свойствам объекта класса в коде инициализации, добавив список назначений формы `property = value` на список аргументов для конструктора.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="6b2a5-148">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="6b2a5-149">Следующая версия приведенного выше кода иллюстрирует сочетание обычных аргументов, необязательные аргументы и параметры свойств в одном вызове конструктора.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a><span data-ttu-id="6b2a5-150">Конструкторы в унаследованном классе</span><span class="sxs-lookup"><span data-stu-id="6b2a5-150">Constructors in inherited class</span></span>
<span data-ttu-id="6b2a5-151">При наследовании от базового класса, который содержит конструктор, необходимо указать ее аргументы в предложении наследовать.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="6b2a5-152">Дополнительные сведения см. в разделе [конструкторы и наследование](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="6b2a5-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="6b2a5-153">Статические конструкторы или конструкторы типов</span><span class="sxs-lookup"><span data-stu-id="6b2a5-153">Static Constructors or Type Constructors</span></span>
<span data-ttu-id="6b2a5-154">Помимо задания кода для создания объектов, статические `let` и `do` привязок, которые могут быть созданы на типы классов, которые выполняются до первого использования типа для инициализации на уровне типа.</span><span class="sxs-lookup"><span data-stu-id="6b2a5-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="6b2a5-155">Дополнительные сведения см. в разделе [ `let` привязок в классах](let-bindings-in-classes.md) и [ `do` привязок в классах](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6b2a5-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b2a5-156">См. также</span><span class="sxs-lookup"><span data-stu-id="6b2a5-156">See Also</span></span>
[<span data-ttu-id="6b2a5-157">Члены</span><span class="sxs-lookup"><span data-stu-id="6b2a5-157">Members</span></span>](index.md)
