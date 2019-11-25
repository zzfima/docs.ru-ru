---
title: Методы
description: Узнайте, как F# метод — это функция, связанная с типом, который используется для предоставления и реализации функциональности и поведения объектов и типов.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976648"
---
# <a name="methods"></a><span data-ttu-id="d07d8-103">Методы</span><span class="sxs-lookup"><span data-stu-id="d07d8-103">Methods</span></span>

<span data-ttu-id="d07d8-104">*Метод* — это функция, которая связана с типом.</span><span class="sxs-lookup"><span data-stu-id="d07d8-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="d07d8-105">В объектно-ориентированном программировании методы используются для предоставления и реализации функциональных возможностей и поведения объектов и типов.</span><span class="sxs-lookup"><span data-stu-id="d07d8-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="d07d8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d07d8-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="d07d8-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="d07d8-107">Remarks</span></span>

<span data-ttu-id="d07d8-108">В предыдущем синтаксисе можно увидеть различные формы объявлений и определений методов.</span><span class="sxs-lookup"><span data-stu-id="d07d8-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="d07d8-109">В более длинных теле метода разрыв строки следует за знаком равенства (=), а весь текст метода — с отступом.</span><span class="sxs-lookup"><span data-stu-id="d07d8-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="d07d8-110">Атрибуты могут применяться к любому объявлению метода.</span><span class="sxs-lookup"><span data-stu-id="d07d8-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="d07d8-111">Они предшествуют синтаксису определения метода и обычно перечисляются в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="d07d8-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="d07d8-112">Дополнительные сведения см. в разделе [Атрибуты](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d07d8-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="d07d8-113">Методы могут быть помечены `inline`.</span><span class="sxs-lookup"><span data-stu-id="d07d8-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="d07d8-114">Сведения о `inline` см. в статье [Встраиваемые функции](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d07d8-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="d07d8-115">Невстроенные методы можно использовать рекурсивно в пределах типа. нет необходимости явно использовать ключевое слово `rec`.</span><span class="sxs-lookup"><span data-stu-id="d07d8-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="d07d8-116">Методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="d07d8-116">Instance Methods</span></span>

<span data-ttu-id="d07d8-117">Методы экземпляра объявляются с помощью ключевого слова `member` и *самоидентификатора*, за которым следует точка (.) и имя и параметры метода.</span><span class="sxs-lookup"><span data-stu-id="d07d8-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="d07d8-118">Как и в случае с `let`ными привязками, *параметр-List* может быть шаблоном.</span><span class="sxs-lookup"><span data-stu-id="d07d8-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="d07d8-119">Как правило, параметры метода заключаются в круглые скобки в форме кортежа, то есть методы отображаются в F# , когда они создаются на других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d07d8-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="d07d8-120">Однако также часто встречается каррированных формы (параметры, разделенные пробелами), а также поддерживаются и другие шаблоны.</span><span class="sxs-lookup"><span data-stu-id="d07d8-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="d07d8-121">В следующем примере показано определение и использование неабстрактного метода экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d07d8-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="d07d8-122">В методах экземпляра не используйте собственный идентификатор для доступа к полям, определенным с помощью привязок let.</span><span class="sxs-lookup"><span data-stu-id="d07d8-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="d07d8-123">Используйте собственный идентификатор при доступе к другим членам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="d07d8-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="d07d8-124">Статические методы</span><span class="sxs-lookup"><span data-stu-id="d07d8-124">Static Methods</span></span>

<span data-ttu-id="d07d8-125">Ключевое слово `static` используется, чтобы указать, что метод может быть вызван без экземпляра и не связан с экземпляром объекта.</span><span class="sxs-lookup"><span data-stu-id="d07d8-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="d07d8-126">В противном случае методы являются методами экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d07d8-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="d07d8-127">В примере в следующем разделе показаны поля, объявленные с ключевым словом `let`, членами свойств, объявленными с ключевым словом `member`, и статическим методом, объявленным с помощью ключевого слова `static`.</span><span class="sxs-lookup"><span data-stu-id="d07d8-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="d07d8-128">В следующем примере показано определение и использование статических методов.</span><span class="sxs-lookup"><span data-stu-id="d07d8-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="d07d8-129">Предположим, что эти определения методов находятся в классе `SomeType` в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="d07d8-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="d07d8-130">Абстрактные и виртуальные методы</span><span class="sxs-lookup"><span data-stu-id="d07d8-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="d07d8-131">Ключевое слово `abstract` указывает, что метод имеет виртуальный слот диспетчеризации и может не иметь определения в классе.</span><span class="sxs-lookup"><span data-stu-id="d07d8-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="d07d8-132">*Виртуальный слот диспетчеризации* — это запись во внутренней таблице функций, которая используется во время выполнения для поиска вызовов виртуальных функций в объектно-ориентированном типе.</span><span class="sxs-lookup"><span data-stu-id="d07d8-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="d07d8-133">Виртуальный механизм диспетчеризации — это механизм, который реализует *полиморфизм*, важный компонент объектно-ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="d07d8-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="d07d8-134">Класс, имеющий по крайней мере один абстрактный метод без определения, является *абстрактным классом*, что означает, что экземпляры этого класса создавать нельзя.</span><span class="sxs-lookup"><span data-stu-id="d07d8-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="d07d8-135">Дополнительные сведения о абстрактных классах см. в разделе [абстрактные классы](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="d07d8-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="d07d8-136">Объявления абстрактных методов не включают тело метода.</span><span class="sxs-lookup"><span data-stu-id="d07d8-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="d07d8-137">Вместо этого за именем метода следует двоеточие (:) и сигнатура типа для метода.</span><span class="sxs-lookup"><span data-stu-id="d07d8-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="d07d8-138">Сигнатура типа метода такая же, как и при использовании IntelliSense при наведении указателя мыши на имя метода в редакторе Visual Studio Code, за исключением случаев, когда имена параметров не указаны.</span><span class="sxs-lookup"><span data-stu-id="d07d8-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="d07d8-139">Сигнатуры типов также отображаются интерпретатором (FSI. exe) при работе в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="d07d8-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="d07d8-140">Сигнатура типа метода формируется путем перечисления типов параметров, за которыми следует возвращаемый тип с соответствующими символами-разделителями.</span><span class="sxs-lookup"><span data-stu-id="d07d8-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="d07d8-141">Каррированных параметра разделяются `->` и параметры кортежа разделяются `*`.</span><span class="sxs-lookup"><span data-stu-id="d07d8-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="d07d8-142">Возвращаемое значение всегда отделяется от аргументов `->` символом.</span><span class="sxs-lookup"><span data-stu-id="d07d8-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="d07d8-143">Круглые скобки можно использовать для группирования сложных параметров, например, если тип функции является параметром или чтобы указать, когда кортеж обрабатывается как один параметр, а не как два параметра.</span><span class="sxs-lookup"><span data-stu-id="d07d8-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="d07d8-144">Можно также предоставить определения абстрактных методов по умолчанию, добавив определение в класс и используя ключевое слово `default`, как показано в блоке синтаксиса в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d07d8-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="d07d8-145">Абстрактный метод, имеющий определение в том же классе, эквивалентен виртуальному методу на других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d07d8-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="d07d8-146">Независимо от того, существует ли определение, ключевое слово `abstract` создает новый слот диспетчеризации в таблице виртуальной функции для класса.</span><span class="sxs-lookup"><span data-stu-id="d07d8-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="d07d8-147">Независимо от того, реализует ли базовый класс его абстрактные методы, производные классы могут предоставлять реализации абстрактных методов.</span><span class="sxs-lookup"><span data-stu-id="d07d8-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="d07d8-148">Чтобы реализовать абстрактный метод в производном классе, определите метод с тем же именем и сигнатурой в производном классе, за исключением использования ключевого слова `override` или `default` и предоставления тела метода.</span><span class="sxs-lookup"><span data-stu-id="d07d8-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="d07d8-149">Ключевые слова `override` и `default` означают точно то же самое.</span><span class="sxs-lookup"><span data-stu-id="d07d8-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="d07d8-150">Используйте `override`, если новый метод переопределяет реализацию базового класса; Используйте `default` при создании реализации в том же классе, что и исходное абстрактное объявление.</span><span class="sxs-lookup"><span data-stu-id="d07d8-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="d07d8-151">Не используйте ключевое слово `abstract` в методе, который реализует метод, объявленный абстрактным в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="d07d8-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="d07d8-152">В следующем примере показан абстрактный метод `Rotate` с реализацией по умолчанию, эквивалентом виртуального метода .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d07d8-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="d07d8-153">В следующем примере показан производный класс, переопределяющий метод базового класса.</span><span class="sxs-lookup"><span data-stu-id="d07d8-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="d07d8-154">В этом случае переопределение изменяет поведение таким образом, чтобы метод не выполнит никаких действий.</span><span class="sxs-lookup"><span data-stu-id="d07d8-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="d07d8-155">Перегруженные методы</span><span class="sxs-lookup"><span data-stu-id="d07d8-155">Overloaded Methods</span></span>

<span data-ttu-id="d07d8-156">Перегруженные методы — это методы, имеющие одинаковые имена в заданном типе, но имеющие разные аргументы.</span><span class="sxs-lookup"><span data-stu-id="d07d8-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="d07d8-157">В F#необязательные аргументы обычно используются вместо перегруженных методов.</span><span class="sxs-lookup"><span data-stu-id="d07d8-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="d07d8-158">Однако перегруженные методы разрешены на языке, при условии, что аргументы находятся в виде кортежа, а не в каррированных форме.</span><span class="sxs-lookup"><span data-stu-id="d07d8-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="d07d8-159">Необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="d07d8-159">Optional Arguments</span></span>

<span data-ttu-id="d07d8-160">Начиная с F# 4,1, можно также иметь необязательные аргументы со значением параметра по умолчанию в методах.</span><span class="sxs-lookup"><span data-stu-id="d07d8-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="d07d8-161">Это помогает упростить взаимодействие с C# кодом.</span><span class="sxs-lookup"><span data-stu-id="d07d8-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="d07d8-162">Следующий пример демонстрирует синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d07d8-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="d07d8-163">Обратите внимание, что значение, передаваемое для `DefaultParameterValue`, должно соответствовать типу входных данных.</span><span class="sxs-lookup"><span data-stu-id="d07d8-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="d07d8-164">В приведенном выше примере это `int`.</span><span class="sxs-lookup"><span data-stu-id="d07d8-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="d07d8-165">Попытка передать нецелочисленное значение в `DefaultParameterValue` приведет к ошибке компиляции.</span><span class="sxs-lookup"><span data-stu-id="d07d8-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="d07d8-166">Пример: свойства и методы</span><span class="sxs-lookup"><span data-stu-id="d07d8-166">Example: Properties and Methods</span></span>

<span data-ttu-id="d07d8-167">В следующем примере содержится тип, который содержит примеры полей, закрытых функций, свойств и статического метода.</span><span class="sxs-lookup"><span data-stu-id="d07d8-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="d07d8-168">См. также</span><span class="sxs-lookup"><span data-stu-id="d07d8-168">See also</span></span>

- [<span data-ttu-id="d07d8-169">Члены</span><span class="sxs-lookup"><span data-stu-id="d07d8-169">Members</span></span>](index.md)
