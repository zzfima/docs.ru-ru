---
title: Методы
description: Узнайте, как метод F-программы — это функция, связанная с типом, который используется для разоблачения и реализации функциональности и поведения объектов и типов.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401067"
---
# <a name="methods"></a><span data-ttu-id="784ba-103">Методы</span><span class="sxs-lookup"><span data-stu-id="784ba-103">Methods</span></span>

<span data-ttu-id="784ba-104">*Метод* — это функция, связанная с типом.</span><span class="sxs-lookup"><span data-stu-id="784ba-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="784ba-105">В объектно-ориентированном программировании методы используются для выявления и реализации функциональности и поведения объектов и типов.</span><span class="sxs-lookup"><span data-stu-id="784ba-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="784ba-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="784ba-106">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="784ba-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="784ba-107">Remarks</span></span>

<span data-ttu-id="784ba-108">В предыдущем синтаксисе можно увидеть различные формы методологии деклараций и определений.</span><span class="sxs-lookup"><span data-stu-id="784ba-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="784ba-109">В более длинных телах метода разрыв строки следует за равным знаком (к), и весь корпус метода отступом.</span><span class="sxs-lookup"><span data-stu-id="784ba-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="784ba-110">Атрибуты могут быть применены к любому методу объявления.</span><span class="sxs-lookup"><span data-stu-id="784ba-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="784ba-111">Они предшествуют синтаксису для определения метода и обычно перечислены в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="784ba-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="784ba-112">Дополнительные сведения см. в разделе [Атрибуты](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="784ba-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="784ba-113">Методы могут `inline`быть помечены.</span><span class="sxs-lookup"><span data-stu-id="784ba-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="784ba-114">Сведения о `inline` см. в статье [Встраиваемые функции](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="784ba-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="784ba-115">Нелайн-методы могут быть использованы рекурсивно в пределах типа; нет необходимости явно использовать `rec` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="784ba-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="784ba-116">Методы инстанции</span><span class="sxs-lookup"><span data-stu-id="784ba-116">Instance Methods</span></span>

<span data-ttu-id="784ba-117">Методы инстанции объявляются с помощью ключевого `member` слова и *самоисждательного,* за которым следует период (.) и имя и параметры метода.</span><span class="sxs-lookup"><span data-stu-id="784ba-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="784ba-118">Как и в `let` случае с привязками, *список параметров* может быть шаблоном.</span><span class="sxs-lookup"><span data-stu-id="784ba-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="784ba-119">Как правило, параметры метода в скобках включаются в форму tuple, что является способом отображаются в F-образном, когда они создаются на других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="784ba-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="784ba-120">Тем не менее, карри форма (параметры, разделенные пространствами) также является общим, и другие модели поддерживаются также.</span><span class="sxs-lookup"><span data-stu-id="784ba-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="784ba-121">Ниже приводится следующий пример, иллюстрирующий определение и использование неабстрактного метода экземпляра.</span><span class="sxs-lookup"><span data-stu-id="784ba-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="784ba-122">В рамках методов экземпляра не используйте самоидентификатор для доступа к полям, определенным с помощью обязательных привязок.</span><span class="sxs-lookup"><span data-stu-id="784ba-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="784ba-123">Используйте самоидентификатор при доступе к другим членам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="784ba-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="784ba-124">Статические методы</span><span class="sxs-lookup"><span data-stu-id="784ba-124">Static Methods</span></span>

<span data-ttu-id="784ba-125">Ключевое `static` слово используется для указания того, что метод может вызываться без экземпляра и не связан с экземпляром объекта.</span><span class="sxs-lookup"><span data-stu-id="784ba-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="784ba-126">В противном случае методы являются методами экземпляра.</span><span class="sxs-lookup"><span data-stu-id="784ba-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="784ba-127">Пример в следующем разделе показывает поля, объявленные `let` с ключевым `member` словом, члены свойства, `static` объявленные с ключевым словом, и статический метод, объявленный с ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="784ba-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="784ba-128">Следующий пример иллюстрирует определение и использование статических методов.</span><span class="sxs-lookup"><span data-stu-id="784ba-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="784ba-129">Предположим, что эти определения `SomeType` метода находятся в классе в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="784ba-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="784ba-130">Абстрактные и виртуальные методы</span><span class="sxs-lookup"><span data-stu-id="784ba-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="784ba-131">Ключевое `abstract` слово указывает на то, что метод имеет виртуальный слот отправки и может не иметь определения в классе.</span><span class="sxs-lookup"><span data-stu-id="784ba-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="784ba-132">*Виртуальный слот для отправки* — это запись во внутренне поддерживаемой таблице функций, которая используется во время выполнения для поиска виртуальных вызовов функций в объектно-ориентированном типе.</span><span class="sxs-lookup"><span data-stu-id="784ba-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="784ba-133">Виртуальный механизм диспетчеризации является механизмом, который реализует *полиморфизм,* важная особенность объектно-ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="784ba-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="784ba-134">Класс, который имеет по крайней мере один абстрактный метод без определения, является *абстрактным классом,* что означает, что не может быть создано ни одного экземпляра этого класса.</span><span class="sxs-lookup"><span data-stu-id="784ba-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="784ba-135">Для получения дополнительной информации об абстрактных классах [см.](../abstract-classes.md)</span><span class="sxs-lookup"><span data-stu-id="784ba-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="784ba-136">Абстрактные методы деклараций не включают в себя тело метода.</span><span class="sxs-lookup"><span data-stu-id="784ba-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="784ba-137">Вместо этого за названием метода следует толстая кишка (:) и подпись типа для метода.</span><span class="sxs-lookup"><span data-stu-id="784ba-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="784ba-138">Подпись типа метода такая же, как и у IntelliSense при приостановке указателя мыши над именем метода в редакторе кода Visual Studio, за исключением имен параметров.</span><span class="sxs-lookup"><span data-stu-id="784ba-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="784ba-139">Тип подписи также отображаются переводчиком, fsi.exe, когда вы работаете в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="784ba-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="784ba-140">Подпись типа метода формируется путем перечисления типов параметров, за которыми следует тип возврата, с соответствующими символами сепаратора.</span><span class="sxs-lookup"><span data-stu-id="784ba-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="784ba-141">Параметры карри разделены параметрами `->` tuple . `*`</span><span class="sxs-lookup"><span data-stu-id="784ba-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="784ba-142">Значение возврата всегда отделяется от `->` аргументов символом.</span><span class="sxs-lookup"><span data-stu-id="784ba-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="784ba-143">Parentheses можно использовать для группировать сложные параметры, such as когда тип функции параметр, или указать когда tuple обработано как одиночный параметр rather than как 2 параметра.</span><span class="sxs-lookup"><span data-stu-id="784ba-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="784ba-144">Можно также дать абстрактные методы определений по умолчанию, добавив определение в класс и используя `default` ключевое слово, как показано в блоке синтаксиса в этой теме.</span><span class="sxs-lookup"><span data-stu-id="784ba-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="784ba-145">Абстрактный метод с определением в том же классе эквивалентен виртуальному методу на других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="784ba-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="784ba-146">Независимо от того, существует `abstract` ли определение, ключевое слово создает новый слот отправки в виртуальной таблице функций для класса.</span><span class="sxs-lookup"><span data-stu-id="784ba-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="784ba-147">Независимо от того, реализует ли базовый класс свои абстрактные методы, выведенные классы могут обеспечить реализацию абстрактных методов.</span><span class="sxs-lookup"><span data-stu-id="784ba-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="784ba-148">Для реализации абстрактного метода в производном классе определите метод, который `override` имеет `default` то же имя и подпись в производном классе, за исключением использования или ключевого слова, и предоставьте тело метода.</span><span class="sxs-lookup"><span data-stu-id="784ba-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="784ba-149">Ключевые `override` слова `default` и означает точно то же самое.</span><span class="sxs-lookup"><span data-stu-id="784ba-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="784ba-150">Используйте, `override` если новый метод перекрывает реализацию базового класса; использовать `default` при создании реализации в том же классе, что и исходная абстрактная декларация.</span><span class="sxs-lookup"><span data-stu-id="784ba-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="784ba-151">Не используйте `abstract` ключевое слово в методе, который реализует метод, объявленный абстрактным в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="784ba-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="784ba-152">Следующий пример иллюстрирует абстрактный метод, `Rotate` который имеет реализацию по умолчанию, эквивалент виртуального метода .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="784ba-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="784ba-153">Следующий пример иллюстрирует производный класс, который переопределяет метод базового класса.</span><span class="sxs-lookup"><span data-stu-id="784ba-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="784ba-154">В этом случае переопределение изменяет поведение таким образом, что метод ничего не делает.</span><span class="sxs-lookup"><span data-stu-id="784ba-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="784ba-155">Перегруженные методы</span><span class="sxs-lookup"><span data-stu-id="784ba-155">Overloaded Methods</span></span>

<span data-ttu-id="784ba-156">Перегруженные методы являются методами, которые имеют одинаковые имена в данном типе, но имеют разные аргументы.</span><span class="sxs-lookup"><span data-stu-id="784ba-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="784ba-157">В ФЗ, как правило, вместо перегруженных методов используются дополнительные аргументы.</span><span class="sxs-lookup"><span data-stu-id="784ba-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="784ba-158">Тем не менее, перегруженные методы допускаются в языке, при условии, что аргументы находятся в форме tuple, а не карри форме.</span><span class="sxs-lookup"><span data-stu-id="784ba-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="784ba-159">Необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="784ba-159">Optional Arguments</span></span>

<span data-ttu-id="784ba-160">Начиная с F-4.1, вы также можете иметь дополнительные аргументы со значением параметра по умолчанию в методах.</span><span class="sxs-lookup"><span data-stu-id="784ba-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="784ba-161">Это поможет облегчить взаимодействие с кодом C'.</span><span class="sxs-lookup"><span data-stu-id="784ba-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="784ba-162">Следующий пример демонстрирует синтаксис:</span><span class="sxs-lookup"><span data-stu-id="784ba-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="784ba-163">Обратите внимание, что `DefaultParameterValue` значение, передаваемые для обязательного соответствия типу ввода.</span><span class="sxs-lookup"><span data-stu-id="784ba-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="784ba-164">В приведенном выше примере, это `int`.</span><span class="sxs-lookup"><span data-stu-id="784ba-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="784ba-165">Попытка передать значение, не являющееся `DefaultParameterValue` все более ценным, приведет к ошибке компиляции.</span><span class="sxs-lookup"><span data-stu-id="784ba-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="784ba-166">Пример: Свойства и методы</span><span class="sxs-lookup"><span data-stu-id="784ba-166">Example: Properties and Methods</span></span>

<span data-ttu-id="784ba-167">Следующий пример содержит тип, содержащий примеры полей, частных функций, свойств и статического метода.</span><span class="sxs-lookup"><span data-stu-id="784ba-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="784ba-168">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="784ba-168">See also</span></span>

- [<span data-ttu-id="784ba-169">Членов</span><span class="sxs-lookup"><span data-stu-id="784ba-169">Members</span></span>](index.md)
