---
title: Методы (F#)
description: 'Узнайте, как метод F # — это функция, связанный с типом, которые используются для предоставления и реализовать функциональность и поведение объектов и типов.'
ms.date: 05/16/2016
ms.openlocfilehash: 02d5a7d22d1ce79a06e15462637c373b33623f61
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253212"
---
# <a name="methods"></a><span data-ttu-id="b573f-103">Методы</span><span class="sxs-lookup"><span data-stu-id="b573f-103">Methods</span></span>

<span data-ttu-id="b573f-104">Объект *метод* — это функция, которая связана с типом.</span><span class="sxs-lookup"><span data-stu-id="b573f-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="b573f-105">В объектно ориентированном программировании методы используются для предоставления и реализовать функциональность и поведение объектов и типов.</span><span class="sxs-lookup"><span data-stu-id="b573f-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="b573f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b573f-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b573f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b573f-107">Remarks</span></span>

<span data-ttu-id="b573f-108">В приведенном выше синтаксисе вы увидите различные формы метод объявлений и определений.</span><span class="sxs-lookup"><span data-stu-id="b573f-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="b573f-109">В телах длинных методов разрыв строки следует знак равенства (=), и все тело метода отображается с отступом.</span><span class="sxs-lookup"><span data-stu-id="b573f-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="b573f-110">Атрибуты могут применяться к любому объявлению метода.</span><span class="sxs-lookup"><span data-stu-id="b573f-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="b573f-111">Они предшествовать синтаксис для определения метода и обычно отображается на отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="b573f-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="b573f-112">Дополнительные сведения см. в разделе [Атрибуты](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="b573f-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="b573f-113">Методы могут быть отмечены `inline`.</span><span class="sxs-lookup"><span data-stu-id="b573f-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="b573f-114">Сведения о `inline` см. в статье [Встраиваемые функции](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="b573f-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="b573f-115">Non встроенные методы можно рекурсивно использовать внутри типа; Нет необходимости явно использовать `rec` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b573f-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="b573f-116">Методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="b573f-116">Instance Methods</span></span>

<span data-ttu-id="b573f-117">Методы экземпляра должны быть объявлены с `member` ключевое слово и *собственный идентификатор*, а затем точку (.), имя метода и параметры.</span><span class="sxs-lookup"><span data-stu-id="b573f-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="b573f-118">Как в случае `let` привязок, *список параметров* может быть шаблоном.</span><span class="sxs-lookup"><span data-stu-id="b573f-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="b573f-119">Как правило заключите метод следования параметров в скобки в форме кортежа, который является образом методы в F # при их создании на других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b573f-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="b573f-120">Тем не менее каррированные (параметров, разделенных пробелами) также характерен и также поддерживаются другие шаблоны.</span><span class="sxs-lookup"><span data-stu-id="b573f-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="b573f-121">Следующий пример иллюстрирует определение и использование метода экземпляра, не являющемся абстрактным.</span><span class="sxs-lookup"><span data-stu-id="b573f-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="b573f-122">Внутри методы экземпляра не используйте собственный идентификатор для доступа к полям, определенный с помощью привязки let.</span><span class="sxs-lookup"><span data-stu-id="b573f-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="b573f-123">При доступе к другие элементы и свойства, используйте собственный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="b573f-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="b573f-124">Статические методы</span><span class="sxs-lookup"><span data-stu-id="b573f-124">Static Methods</span></span>

<span data-ttu-id="b573f-125">Ключевое слово `static` используется для указания, что метод может вызываться без экземпляра и не связан с экземпляром объекта.</span><span class="sxs-lookup"><span data-stu-id="b573f-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="b573f-126">В противном случае методы являются методами экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b573f-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="b573f-127">В примере в следующем разделе показаны поля, объявленные с `let` ключевое слово, свойства, объявленные с `member` ключевое слово и статический метод, объявленный с `static` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="b573f-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="b573f-128">Следующий пример иллюстрирует определение и использование статических методов.</span><span class="sxs-lookup"><span data-stu-id="b573f-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="b573f-129">Предполагается, что определения этих методов — в `SomeType` класс в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="b573f-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="b573f-130">Абстрактные и виртуальные методы</span><span class="sxs-lookup"><span data-stu-id="b573f-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="b573f-131">Ключевое слово `abstract` указывает, что метод имеет виртуальная ячейка отправки и не может иметь определение в классе.</span><span class="sxs-lookup"><span data-stu-id="b573f-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="b573f-132">Объект *виртуальная ячейка отправки* — это запись во внутренней таблице функций, используемый для поиска виртуальных функций во время выполнения вызовов в типе объектно ориентированного.</span><span class="sxs-lookup"><span data-stu-id="b573f-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="b573f-133">Механизм виртуальной отправки — это механизм, который реализует *полиморфизм*, важной характеристикой объектно ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="b573f-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="b573f-134">Является классом, имеющим по крайней мере один абстрактный метод без определения *абстрактного класса*, что означает, что экземпляры не могут создаваться этого класса.</span><span class="sxs-lookup"><span data-stu-id="b573f-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="b573f-135">Дополнительные сведения об абстрактных классах см. в разделе [абстрактные классы](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b573f-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="b573f-136">Объявления абстрактных методов не содержат тела метода.</span><span class="sxs-lookup"><span data-stu-id="b573f-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="b573f-137">Вместо этого имя метода следует двоеточие (:) и сигнатура типа для метода.</span><span class="sxs-lookup"><span data-stu-id="b573f-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="b573f-138">Сигнатура типа метода совпадает со значением, отображаемым с помощью IntelliSense при наведении указателя мыши на имени метода в редакторе кода Visual Studio, за исключением без имен параметров.</span><span class="sxs-lookup"><span data-stu-id="b573f-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="b573f-139">Сигнатуры типов также отображаются интерпретатором fsi.exe, во время работы в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="b573f-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="b573f-140">Сигнатура типа метода формируется перечислением типы параметров и типом возвращаемого значения, с соответствующими символами-разделителями.</span><span class="sxs-lookup"><span data-stu-id="b573f-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="b573f-141">Разделенные каррированные параметры `->` и разделяются кортежах `*`.</span><span class="sxs-lookup"><span data-stu-id="b573f-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="b573f-142">Возвращаемое значение всегда отделяется от аргументов по `->` символов.</span><span class="sxs-lookup"><span data-stu-id="b573f-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="b573f-143">Можно использовать скобки для группирования сложные параметры, например, если типом функции параметра, или чтобы указать, когда обрабатывается кортеж в качестве единственного параметра, а не как два параметра.</span><span class="sxs-lookup"><span data-stu-id="b573f-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="b573f-144">Вы можете также давать абстрактные методы определения по умолчанию путем добавления определения класса и с помощью `default` ключевое слово, как показано в приведенном в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b573f-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="b573f-145">Абстрактный метод, который определен в том же классе соответствует виртуальный метод на других языках .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b573f-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="b573f-146">Существует ли определение, `abstract` ключевое слово создает новую ячейку отправки в таблице виртуальных функций для класса.</span><span class="sxs-lookup"><span data-stu-id="b573f-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="b573f-147">Независимо от того, является ли базовый класс реализует свои абстрактные методы производные классы могут предоставлять реализации абстрактных методов.</span><span class="sxs-lookup"><span data-stu-id="b573f-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="b573f-148">Чтобы реализовать абстрактный метод в производном классе, определите метод, который имеет то же имя и подпись в производном классе, за исключением использования `override` или `default` ключевое слово и укажите основной части метода.</span><span class="sxs-lookup"><span data-stu-id="b573f-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="b573f-149">Ключевые слова `override` и `default` означает то же.</span><span class="sxs-lookup"><span data-stu-id="b573f-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="b573f-150">Используйте `override` Если новый метод переопределяет реализацию базового класса; используйте `default` при создании реализация в тот же класс как абстрактный исходного объявления.</span><span class="sxs-lookup"><span data-stu-id="b573f-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="b573f-151">Не используйте `abstract` ключевое слово на метод, который реализует метод, объявленный в базовом классе как абстрактный.</span><span class="sxs-lookup"><span data-stu-id="b573f-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="b573f-152">В следующем примере показан абстрактный метод `Rotate` , имеет реализацию по умолчанию, эквивалент виртуальный метод .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b573f-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="b573f-153">В следующем примере производный класс, который переопределяет метод базового класса.</span><span class="sxs-lookup"><span data-stu-id="b573f-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="b573f-154">В этом случае переопределение изменяет поведение, чтобы метод не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="b573f-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="b573f-155">Перегруженные методы</span><span class="sxs-lookup"><span data-stu-id="b573f-155">Overloaded Methods</span></span>

<span data-ttu-id="b573f-156">Перегруженные методы являются методами, имеющие идентичные имена для данного типа, но разные аргументы.</span><span class="sxs-lookup"><span data-stu-id="b573f-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="b573f-157">В F # вместо перегруженных методов обычно используются необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="b573f-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="b573f-158">Тем не менее при условии, что аргументы имеют в форме кортежа, не каррированные перегруженные методы разрешены на языке.</span><span class="sxs-lookup"><span data-stu-id="b573f-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="b573f-159">Необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="b573f-159">Optional Arguments</span></span>

<span data-ttu-id="b573f-160">Начиная с F # 4.1, может также иметь необязательные аргументы со значением параметра по умолчанию в методах.</span><span class="sxs-lookup"><span data-stu-id="b573f-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="b573f-161">Это помогает упростить взаимодействие с кодом C#.</span><span class="sxs-lookup"><span data-stu-id="b573f-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="b573f-162">Следующий пример демонстрирует синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b573f-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="b573f-163">Обратите внимание, что значение, переданное в для `DefaultParameterValue` должен совпадать с типом ввода.</span><span class="sxs-lookup"><span data-stu-id="b573f-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="b573f-164">В приведенном выше примере это `int`.</span><span class="sxs-lookup"><span data-stu-id="b573f-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="b573f-165">Попытка передать нецелочисленное значение в `DefaultParameterValue` приведет к ошибке компиляции.</span><span class="sxs-lookup"><span data-stu-id="b573f-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="b573f-166">Пример: Свойства и методы</span><span class="sxs-lookup"><span data-stu-id="b573f-166">Example: Properties and Methods</span></span>

<span data-ttu-id="b573f-167">Следующий пример содержит тип, который содержит примеры полей, закрытые функции, свойства и статический метод.</span><span class="sxs-lookup"><span data-stu-id="b573f-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="b573f-168">См. также</span><span class="sxs-lookup"><span data-stu-id="b573f-168">See also</span></span>

- [<span data-ttu-id="b573f-169">Члены</span><span class="sxs-lookup"><span data-stu-id="b573f-169">Members</span></span>](index.md)
