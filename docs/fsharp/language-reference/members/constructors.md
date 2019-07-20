---
title: Конструкторы
description: Узнайте, как определять и использовать конструкторы в F# для создания и инициализации объектов класса и структуры.
ms.date: 05/16/2016
ms.openlocfilehash: ef5dc134ad98179b6a365c4c34a9eca22fe5f7f6
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364357"
---
# <a name="constructors"></a><span data-ttu-id="6561d-103">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="6561d-103">Constructors</span></span>

<span data-ttu-id="6561d-104">В этом разделе описывается определение и использование конструкторов для создания и инициализации объектов класса и структуры.</span><span class="sxs-lookup"><span data-stu-id="6561d-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="6561d-105">Создание объектов класса</span><span class="sxs-lookup"><span data-stu-id="6561d-105">Construction of Class Objects</span></span>

<span data-ttu-id="6561d-106">Объекты типов классов имеют конструкторы.</span><span class="sxs-lookup"><span data-stu-id="6561d-106">Objects of class types have constructors.</span></span> <span data-ttu-id="6561d-107">Существует два вида конструкторов.</span><span class="sxs-lookup"><span data-stu-id="6561d-107">There are two kinds of constructors.</span></span> <span data-ttu-id="6561d-108">Один из них является основным конструктором, параметры которого отображаются в круглых скобках сразу после имени типа.</span><span class="sxs-lookup"><span data-stu-id="6561d-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="6561d-109">Другие, необязательные дополнительные конструкторы указываются с `new` помощью ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="6561d-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="6561d-110">Все такие дополнительные конструкторы должны вызывать первичный конструктор.</span><span class="sxs-lookup"><span data-stu-id="6561d-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="6561d-111">Первичный конструктор содержит `let` и `do` привязки, которые отображаются в начале определения класса.</span><span class="sxs-lookup"><span data-stu-id="6561d-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="6561d-112">Привязка объявляет закрытые поля и методы класса `do` ; привязка выполняет код. `let`</span><span class="sxs-lookup"><span data-stu-id="6561d-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="6561d-113">Дополнительные сведения о `let` привязках в конструкторах классов см. в разделе [ `let` привязки в классах](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6561d-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="6561d-114">Дополнительные сведения о `do` привязках в конструкторах см. в разделе [ `do` привязки в классах](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6561d-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="6561d-115">Независимо от того, является ли конструктор, который необходимо вызвать, основным конструктором или дополнительным конструктором, можно создавать объекты с помощью `new` выражения с `new` ключевым словом или без него.</span><span class="sxs-lookup"><span data-stu-id="6561d-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="6561d-116">Объекты инициализируются вместе с аргументами конструктора, путем перечисления аргументов по порядку и разделенных запятыми и заключенных в круглые скобки, а также с помощью именованных аргументов и значений в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="6561d-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="6561d-117">Вы также можете задать свойства объекта во время создания объекта, используя имена свойств и назначив значения так же, как при использовании именованных аргументов конструктора.</span><span class="sxs-lookup"><span data-stu-id="6561d-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="6561d-118">В следующем коде показан класс, имеющий конструктор, и различные способы создания объектов.</span><span class="sxs-lookup"><span data-stu-id="6561d-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="6561d-119">Выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6561d-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="6561d-120">Создание структур</span><span class="sxs-lookup"><span data-stu-id="6561d-120">Construction of Structures</span></span>

<span data-ttu-id="6561d-121">Структуры соответствуют всем правилам классов.</span><span class="sxs-lookup"><span data-stu-id="6561d-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="6561d-122">Поэтому у вас может быть первичный конструктор, и можно предоставить дополнительные конструкторы с помощью `new`.</span><span class="sxs-lookup"><span data-stu-id="6561d-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="6561d-123">Однако существует одно важное различие между структурами и классами: структуры могут иметь конструктор без параметров (то есть один без аргументов), даже если первичный конструктор не определен.</span><span class="sxs-lookup"><span data-stu-id="6561d-123">However, there is one important difference between structures and classes: structures can have a parameterless constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="6561d-124">Конструктор без параметров инициализирует все поля значением по умолчанию для этого типа, обычно ноль или его эквивалент.</span><span class="sxs-lookup"><span data-stu-id="6561d-124">The parameterless constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="6561d-125">Все конструкторы, определяемые для структур, должны иметь по крайней мере один аргумент, чтобы они не конфликтовали с конструктором по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6561d-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="6561d-126">Кроме того, структуры часто имеют поля, создаваемые с помощью `val` ключевого слова; классы также могут иметь эти поля.</span><span class="sxs-lookup"><span data-stu-id="6561d-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="6561d-127">Структуры и классы, имеющие поля, определенные с помощью `val` ключевого слова, можно также инициализировать в дополнительных конструкторах с помощью выражений записи, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6561d-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="6561d-128">Дополнительные сведения см. в [разделе явные поля: Ключевое](explicit-fields-the-val-keyword.md)слово. `val`</span><span class="sxs-lookup"><span data-stu-id="6561d-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="6561d-129">Исполнение побочных эффектов в конструкторах</span><span class="sxs-lookup"><span data-stu-id="6561d-129">Executing Side Effects in Constructors</span></span>

<span data-ttu-id="6561d-130">Основной конструктор в классе может выполнять код в `do` привязке.</span><span class="sxs-lookup"><span data-stu-id="6561d-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="6561d-131">Но что делать, если необходимо выполнить код в дополнительном конструкторе без `do` привязки?</span><span class="sxs-lookup"><span data-stu-id="6561d-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="6561d-132">Для этого используется `then` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6561d-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="6561d-133">Побочные эффекты основного конструктора по-прежнему выполняются.</span><span class="sxs-lookup"><span data-stu-id="6561d-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="6561d-134">Поэтому выходные данные выглядят следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6561d-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="6561d-135">Собственные идентификаторы в конструкторах</span><span class="sxs-lookup"><span data-stu-id="6561d-135">Self Identifiers in Constructors</span></span>

<span data-ttu-id="6561d-136">В других элементах вы предоставляете имя для текущего объекта в определении каждого члена.</span><span class="sxs-lookup"><span data-stu-id="6561d-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="6561d-137">Можно также разместить собственный идентификатор в первой строке определения класса с помощью ключевого слова, `as` непосредственно следующего за параметрами конструктора.</span><span class="sxs-lookup"><span data-stu-id="6561d-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="6561d-138">Этот синтаксис показан в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6561d-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="6561d-139">В дополнительных конструкторах можно также определить собственный идентификатор, поместив `as` предложение сразу после параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="6561d-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="6561d-140">Этот синтаксис показан в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6561d-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="6561d-141">Проблемы могут возникать при попытке использования объекта до его полного определения.</span><span class="sxs-lookup"><span data-stu-id="6561d-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="6561d-142">Таким образом, использование собственного идентификатора может привести к тому, что компилятор выдаст предупреждение и вставит дополнительные проверки, чтобы гарантировать, что элементы объекта не будут доступны до инициализации объекта.</span><span class="sxs-lookup"><span data-stu-id="6561d-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="6561d-143">Собственный идентификатор следует использовать только в `do` привязках первичного конструктора или `then` после ключевого слова в дополнительных конструкторах.</span><span class="sxs-lookup"><span data-stu-id="6561d-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="6561d-144">Имя собственного идентификатора не обязательно должно быть `this`.</span><span class="sxs-lookup"><span data-stu-id="6561d-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="6561d-145">Это может быть любой допустимый идентификатор.</span><span class="sxs-lookup"><span data-stu-id="6561d-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="6561d-146">Присвоение значений свойствам при инициализации</span><span class="sxs-lookup"><span data-stu-id="6561d-146">Assigning Values to Properties at Initialization</span></span>

<span data-ttu-id="6561d-147">Можно присвоить значения свойствам объекта класса в коде инициализации, добавив список назначений формы `property = value` в список аргументов для конструктора.</span><span class="sxs-lookup"><span data-stu-id="6561d-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="6561d-148">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6561d-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="6561d-149">Следующая версия предыдущего кода иллюстрирует сочетание обычных аргументов, необязательных аргументов и параметров свойств в одном вызове конструктора.</span><span class="sxs-lookup"><span data-stu-id="6561d-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="6561d-150">Конструкторы в унаследованном классе</span><span class="sxs-lookup"><span data-stu-id="6561d-150">Constructors in inherited class</span></span>

<span data-ttu-id="6561d-151">При наследовании от базового класса, имеющего конструктор, необходимо указать его аргументы в предложении Inherit.</span><span class="sxs-lookup"><span data-stu-id="6561d-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="6561d-152">Дополнительные сведения см. в разделе [конструкторы и наследование](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="6561d-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="6561d-153">Статические конструкторы или конструкторы типов</span><span class="sxs-lookup"><span data-stu-id="6561d-153">Static Constructors or Type Constructors</span></span>

<span data-ttu-id="6561d-154">Помимо указания кода для создания объектов, статические `let` и `do` привязку можно создавать в типах классов, которые выполняются до первого использования типа для выполнения инициализации на уровне типа.</span><span class="sxs-lookup"><span data-stu-id="6561d-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="6561d-155">Дополнительные сведения см. в разделе [ `let` привязки в классах](let-bindings-in-classes.md) и [ `do` привязках в классах](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6561d-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6561d-156">См. также</span><span class="sxs-lookup"><span data-stu-id="6561d-156">See also</span></span>

- [<span data-ttu-id="6561d-157">Члены</span><span class="sxs-lookup"><span data-stu-id="6561d-157">Members</span></span>](index.md)
