---
title: Новые возможности C# 6. Руководство по языку C#
description: Сведения о новых возможностях в C# 6
keywords: .NET, .NET Core
author: BillWagner
ms.date: 09/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 4d879f69-f889-4d3f-a781-75194e143400
ms.openlocfilehash: ea54e9a05120134eea8e1bc9d82302a7513b43e7
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="whats-new-in-c-6"></a><span data-ttu-id="016bb-104">Новые возможности C# 6</span><span class="sxs-lookup"><span data-stu-id="016bb-104">What's New in C# 6</span></span>

<span data-ttu-id="016bb-105">Версия C# 6.0 содержит множество функций, помогающих повысить производительность труда разработчиков.</span><span class="sxs-lookup"><span data-stu-id="016bb-105">The 6.0 release of C# contained many features that improve productivity for developers.</span></span> <span data-ttu-id="016bb-106">Ниже приведены функции в этом выпуске.</span><span class="sxs-lookup"><span data-stu-id="016bb-106">Features in this release include:</span></span>

* <span data-ttu-id="016bb-107">[Автосвойства, доступные только для чтения](#read-only-auto-properties).</span><span class="sxs-lookup"><span data-stu-id="016bb-107">[Read-only Auto-properties](#read-only-auto-properties):</span></span>
    - <span data-ttu-id="016bb-108">Можно создавать автосвойства только для чтения, задаваемые только в конструкторах.</span><span class="sxs-lookup"><span data-stu-id="016bb-108">You can create read-only auto-properties that can be set only in constructors.</span></span>
* <span data-ttu-id="016bb-109">[Инициализаторы автосвойств](#auto-property-initializers).</span><span class="sxs-lookup"><span data-stu-id="016bb-109">[Auto-Property Initializers](#auto-property-initializers):</span></span>
    - <span data-ttu-id="016bb-110">Можно написать выражения инициализации для задания первоначального значения автосвойства.</span><span class="sxs-lookup"><span data-stu-id="016bb-110">You can write initialization expressions to set the initial value of an auto-property.</span></span>
* <span data-ttu-id="016bb-111">[Члены функции, воплощающие выражение](#expression-bodied-function-members).</span><span class="sxs-lookup"><span data-stu-id="016bb-111">[Expression-bodied function members](#expression-bodied-function-members):</span></span>
    - <span data-ttu-id="016bb-112">Можно создавать однострочные методы с помощью лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="016bb-112">You can author one-line methods using lambda expressions.</span></span>
* <span data-ttu-id="016bb-113">[using static](#using-static).</span><span class="sxs-lookup"><span data-stu-id="016bb-113">[using static](#using-static):</span></span>
    - <span data-ttu-id="016bb-114">Можно импортировать все методы одного класса в текущее пространство имен.</span><span class="sxs-lookup"><span data-stu-id="016bb-114">You can import all the methods of a single class into the current namespace.</span></span>
* <span data-ttu-id="016bb-115">[NULL — условные операторы](#null-conditional-operators).</span><span class="sxs-lookup"><span data-stu-id="016bb-115">[Null - conditional operators](#null-conditional-operators):</span></span>
    - <span data-ttu-id="016bb-116">Краткий и безопасный доступ к членам объекта с проверкой значения NULL с помощью условного оператора NULL.</span><span class="sxs-lookup"><span data-stu-id="016bb-116">You can concisely and safely access members of an object while still checking for null with the null conditional operator.</span></span>
* <span data-ttu-id="016bb-117">[Интерполяция строк](#string-interpolation).</span><span class="sxs-lookup"><span data-stu-id="016bb-117">[String Interpolation](#string-interpolation):</span></span>
    - <span data-ttu-id="016bb-118">Можно написать выражения форматирования строк, используя встроенные выражения вместо позиционных аргументов.</span><span class="sxs-lookup"><span data-stu-id="016bb-118">You can write string formatting expressions using inline expressions instead of positional arguments.</span></span>
* <span data-ttu-id="016bb-119">[Фильтры исключений](#exception-filters).</span><span class="sxs-lookup"><span data-stu-id="016bb-119">[Exception filters](#exception-filters):</span></span>
    - <span data-ttu-id="016bb-120">Можно перехватывать выражения на основе свойств исключения или другого состояния программы.</span><span class="sxs-lookup"><span data-stu-id="016bb-120">You can catch expressions based on properties of the exception or other program state.</span></span> 
* <span data-ttu-id="016bb-121">[Выражения nameof](#nameof-expressions).</span><span class="sxs-lookup"><span data-stu-id="016bb-121">[nameof Expressions](#nameof-expressions):</span></span>
    - <span data-ttu-id="016bb-122">Можно разрешить компилятору создавать строковые представления символов.</span><span class="sxs-lookup"><span data-stu-id="016bb-122">You can let the compiler generate string representations of symbols.</span></span>
* <span data-ttu-id="016bb-123">[Выражение Await в блоках Catch и Finally](#await-in-catch-and-finally-blocks).</span><span class="sxs-lookup"><span data-stu-id="016bb-123">[await in catch and finally blocks](#await-in-catch-and-finally-blocks):</span></span>
    - <span data-ttu-id="016bb-124">Можно использовать выражения `await` в расположениях, где раньше они были запрещены.</span><span class="sxs-lookup"><span data-stu-id="016bb-124">You can use `await` expressions in locations that previously disallowed them.</span></span>
* <span data-ttu-id="016bb-125">[Инициализаторы индекса](#index-initializers).</span><span class="sxs-lookup"><span data-stu-id="016bb-125">[index initializers](#index-initializers):</span></span>
    - <span data-ttu-id="016bb-126">Можно создавать выражения инициализации для ассоциативных контейнеров, а также контейнеров последовательности.</span><span class="sxs-lookup"><span data-stu-id="016bb-126">You can author initialization expressions for associative containers as well as sequence containers.</span></span>
* <span data-ttu-id="016bb-127">[Методы расширения для инициализаторов коллекций](#extension-add-methods-in-collection-initializers).</span><span class="sxs-lookup"><span data-stu-id="016bb-127">[Extension methods for collection initializers](#extension-add-methods-in-collection-initializers):</span></span>
    - <span data-ttu-id="016bb-128">Инициализаторы коллекций могут зависеть от доступных методов расширения в дополнение к методам-членам.</span><span class="sxs-lookup"><span data-stu-id="016bb-128">Collection initializers can rely on accessible extension methods, in addition to member methods.</span></span>
* <span data-ttu-id="016bb-129">[Улучшенное разрешение перегрузки](#improved-overload-resolution).</span><span class="sxs-lookup"><span data-stu-id="016bb-129">[Improved overload resolution](#improved-overload-resolution):</span></span>
    - <span data-ttu-id="016bb-130">Некоторые конструкции, которые ранее создавали неоднозначные вызовы методов, теперь разрешаются правильно.</span><span class="sxs-lookup"><span data-stu-id="016bb-130">Some constructs that previously generated ambiguous method calls now resolve correctly.</span></span>

<span data-ttu-id="016bb-131">Общим эффектом этих функций является написание более краткого кода, который также является более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="016bb-131">The overall effect of these features is that you write more concise code that is also more readable.</span></span> <span data-ttu-id="016bb-132">Синтаксис содержит меньше формальных элементов для многих общих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="016bb-132">The syntax contains less ceremony for many common practices.</span></span> <span data-ttu-id="016bb-133">Благодаря краткости становится проще понять назначение кода.</span><span class="sxs-lookup"><span data-stu-id="016bb-133">It's easier to see the design intent with less ceremony.</span></span> <span data-ttu-id="016bb-134">Хорошо изучив эти возможности, вы сможете работать более производительно, создавая более читаемый код и уделяя больше внимания основным функциям, а не конструкциям языка.</span><span class="sxs-lookup"><span data-stu-id="016bb-134">Learn these features well, and you'll be more productive, write more readable code, and concentrate more on your core features than on the constructs of the language.</span></span>

<span data-ttu-id="016bb-135">В оставшейся части этого раздела приводятся сведения о каждой из этих функций.</span><span class="sxs-lookup"><span data-stu-id="016bb-135">The remainder of this topic provides details on each of these features.</span></span>

## <a name="auto-property-enhancements"></a><span data-ttu-id="016bb-136">Усовершенствования автосвойств</span><span class="sxs-lookup"><span data-stu-id="016bb-136">Auto-Property enhancements</span></span> 

<span data-ttu-id="016bb-137">Синтаксис автоматически реализуемых свойств (обычно называемых "автосвойствами") значительно упростил создание свойств с простыми методами доступа get и set:</span><span class="sxs-lookup"><span data-stu-id="016bb-137">The syntax for automatically implemented properties (usually referred to as 'auto-properties') made it very easy to create properties that had simple get and set accessors:</span></span>

[!code-csharp[ClassicAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicAutoProperty)]

<span data-ttu-id="016bb-138">Тем не менее этот простой синтаксис ограничивает типы проектов, в которых поддерживаются автосвойства.</span><span class="sxs-lookup"><span data-stu-id="016bb-138">However, this simple syntax limited the kinds of designs you could support using auto-properties.</span></span> <span data-ttu-id="016bb-139">В C# 6 улучшены возможности автосвойств, чтобы их можно было использовать в более широком ряде сценариев.</span><span class="sxs-lookup"><span data-stu-id="016bb-139">C# 6 improves the auto-properties capabilities so that you can use them in more scenarios.</span></span> <span data-ttu-id="016bb-140">Вам не потребуется слишком часто возвращаться к более подробному синтаксису объявления и обработки резервного поля вручную.</span><span class="sxs-lookup"><span data-stu-id="016bb-140">You won't need to fall back on the more verbose syntax of declaring and manipulating the backing field by hand so often.</span></span>

<span data-ttu-id="016bb-141">Новый синтаксис предназначен для сценариев, в которых используются свойства только для чтения и инициализация хранения переменных за пределами автосвойства.</span><span class="sxs-lookup"><span data-stu-id="016bb-141">The new syntax addresses scenarios for read-only properties, and for initializing the variable storage behind an auto-property.</span></span>

### <a name="read-only-auto-properties"></a><span data-ttu-id="016bb-142">Автосвойства, доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="016bb-142">Read-only auto-properties</span></span>

<span data-ttu-id="016bb-143">*Автосвойства только для чтения* предоставляют более краткий синтаксис для создания неизменяемых типов.</span><span class="sxs-lookup"><span data-stu-id="016bb-143">*Read-only auto-properties* provide a more concise syntax to create immutable types.</span></span> <span data-ttu-id="016bb-144">Ближайшим аналогом неизменяемых типов в более ранних версиях C# являлось объявление закрытых методов задания:</span><span class="sxs-lookup"><span data-stu-id="016bb-144">The closest you could get to immutable types in earlier versions of C# was to declare private setters:</span></span>

[!code-csharp[ClassicReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicReadOnlyAutoProperty)]
 
<span data-ttu-id="016bb-145">При использовании этого синтаксиса компилятор не гарантирует, что тип будет действительно неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="016bb-145">Using this syntax, the compiler doesn't ensure that the type really is immutable.</span></span> <span data-ttu-id="016bb-146">Он гарантирует только то, что свойства `FirstName` и `LastName` не изменяются из кода за пределами класса.</span><span class="sxs-lookup"><span data-stu-id="016bb-146">It only enforces that the `FirstName` and `LastName` properties are not modified from any code outside the class.</span></span>

<span data-ttu-id="016bb-147">Автосвойства только для чтения обеспечивают фактическое поведение "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="016bb-147">Read-only auto-properties enable true read-only behavior.</span></span> <span data-ttu-id="016bb-148">Автосвойство объявляется с помощью только метода доступа get:</span><span class="sxs-lookup"><span data-stu-id="016bb-148">You declare the auto-property with only a get accessor:</span></span>

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

<span data-ttu-id="016bb-149">Свойства `FirstName` и `LastName` могут задаваться только в теле конструктора:</span><span class="sxs-lookup"><span data-stu-id="016bb-149">The `FirstName` and `LastName` properties can be set only in the body of a constructor:</span></span>

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

<span data-ttu-id="016bb-150">Попытка задать `LastName` в другом методе создает ошибку компиляции `CS0200`:</span><span class="sxs-lookup"><span data-stu-id="016bb-150">Trying to set `LastName` in another method generates a `CS0200` compilation error:</span></span>

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

<span data-ttu-id="016bb-151">Эта функция обеспечивает действительную поддержку создания неизменяемых типов на уровне языка и использование более краткого и удобного синтаксиса автосвойств.</span><span class="sxs-lookup"><span data-stu-id="016bb-151">This feature enables true language support for creating immutable types and using the more concise and convenient auto-property syntax.</span></span>

### <a name="auto-property-initializers"></a><span data-ttu-id="016bb-152">Инициализаторы автосвойств</span><span class="sxs-lookup"><span data-stu-id="016bb-152">Auto-Property Initializers</span></span>

<span data-ttu-id="016bb-153">*Инициализаторы автосвойств* позволяют объявлять начальное значение для автосвойства при объявлении свойства.</span><span class="sxs-lookup"><span data-stu-id="016bb-153">*Auto-Property Initializers* let you declare the initial value for an auto-property as part of the property declaration.</span></span>  <span data-ttu-id="016bb-154">В более ранних версиях эти свойства должны были иметь методы задания, которые вы бы использовали для инициализации хранилища данных, используемого резервным полем.</span><span class="sxs-lookup"><span data-stu-id="016bb-154">In earlier versions, these properties would need to have setters and you would need to use that setter to initialize the data storage used by the backing field.</span></span> <span data-ttu-id="016bb-155">Рассмотрим этот класс для учащихся, который содержит имена и список их оценок.</span><span class="sxs-lookup"><span data-stu-id="016bb-155">Consider this class for a student that contains the name and a list of the student's grades:</span></span>

[!code-csharp[Construction](../../../samples/snippets/csharp/new-in-6/oldcode.cs#Construction)]
 
<span data-ttu-id="016bb-156">По мере роста этого класса можно включать другие конструкторы.</span><span class="sxs-lookup"><span data-stu-id="016bb-156">As this class grows, you may include other constructors.</span></span> <span data-ttu-id="016bb-157">Каждый конструктор должен инициализировать это поле, или будут создаваться ошибки.</span><span class="sxs-lookup"><span data-stu-id="016bb-157">Each constructor needs to initialize this field, or you'll introduce errors.</span></span>

<span data-ttu-id="016bb-158">C# 6 позволяет задать начальное значение для хранилища, используемого автосвойством в объявлении автосвойства:</span><span class="sxs-lookup"><span data-stu-id="016bb-158">C# 6 enables you to assign an initial value for the storage used by an auto-property in the auto-property declaration:</span></span>

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

<span data-ttu-id="016bb-159">Член `Grades` инициализируется там, где он объявлен.</span><span class="sxs-lookup"><span data-stu-id="016bb-159">The `Grades` member is initialized where it is declared.</span></span> <span data-ttu-id="016bb-160">Это упрощает выполнение инициализации ровно один раз.</span><span class="sxs-lookup"><span data-stu-id="016bb-160">That makes it easier to perform the initialization exactly once.</span></span> <span data-ttu-id="016bb-161">Инициализация является частью объявления свойства, упрощая уравнение выделения хранилища с открытым интерфейсом для объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="016bb-161">The initialization is part of the property declaration, making it easier to equate the storage allocation with public interface for `Student` objects.</span></span>

<span data-ttu-id="016bb-162">Инициализаторы свойств можно использовать со свойствами для чтения и записи, а также со свойствами только для чтения, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="016bb-162">Property Initializers can be used with read/write properties as well as read-only properties, as shown here.</span></span>

[!code-csharp[ReadWriteInitialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadWriteInitialization)]

## <a name="expression-bodied-function-members"></a><span data-ttu-id="016bb-163">Члены функции, воплощающие выражение</span><span class="sxs-lookup"><span data-stu-id="016bb-163">Expression-bodied function members</span></span>

<span data-ttu-id="016bb-164">Тело многих создаваемых нами членов состоит только из одного оператора, который может быть представлен как выражение.</span><span class="sxs-lookup"><span data-stu-id="016bb-164">The body of a lot of members that we write consist of only one statement that can be represented as an expression.</span></span> <span data-ttu-id="016bb-165">Можно сократить этот синтаксис, написав член, воплощающий выражение.</span><span class="sxs-lookup"><span data-stu-id="016bb-165">You can reduce that syntax by writing an expression-bodied member instead.</span></span> <span data-ttu-id="016bb-166">Это работает для методов и свойств, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="016bb-166">It works for methods and read-only properties.</span></span> <span data-ttu-id="016bb-167">Например, переопределение `ToString()` часто бывает отличным кандидатом:</span><span class="sxs-lookup"><span data-stu-id="016bb-167">For example, an override of `ToString()` is often a great candidate:</span></span>

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

<span data-ttu-id="016bb-168">Члены, воплощающие выражение, можно также использовать в свойствах только для чтения:</span><span class="sxs-lookup"><span data-stu-id="016bb-168">You can also use expression-bodied members in read-only properties as well:</span></span>

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

## <a name="using-static"></a><span data-ttu-id="016bb-169">using static</span><span class="sxs-lookup"><span data-stu-id="016bb-169">using static</span></span>

<span data-ttu-id="016bb-170">Усовершенствование *using static* позволяет импортировать статические методы одного класса.</span><span class="sxs-lookup"><span data-stu-id="016bb-170">The *using static* enhancement enables you to import the static methods of a single class.</span></span> <span data-ttu-id="016bb-171">Ранее оператор `using` импортировал все типы в пространство имен.</span><span class="sxs-lookup"><span data-stu-id="016bb-171">Previously, the `using` statement imported all types in a namespace.</span></span> 

<span data-ttu-id="016bb-172">Мы часто используем статические методы класса в коде.</span><span class="sxs-lookup"><span data-stu-id="016bb-172">Often we use a class' static methods throughout our code.</span></span> <span data-ttu-id="016bb-173">Постоянное повторение имени класса может затруднить понимание кода.</span><span class="sxs-lookup"><span data-stu-id="016bb-173">Repeatedly typing the class name can obscure the meaning of your code.</span></span> <span data-ttu-id="016bb-174">Так, например, происходит при написании классов, выполняющих много числовых вычислений.</span><span class="sxs-lookup"><span data-stu-id="016bb-174">A common example is when you write classes that perform many numeric calculations.</span></span>
<span data-ttu-id="016bb-175">Код будет засорен <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> и другими вызовами в различные методы в классе <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="016bb-175">Your code will be littered with <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> and other calls to different methods in the <xref:System.Math> class.</span></span> <span data-ttu-id="016bb-176">Новый синтаксис `using static` повышает читаемость этих классов.</span><span class="sxs-lookup"><span data-stu-id="016bb-176">The new `using static` syntax can make these classes much cleaner to read.</span></span> <span data-ttu-id="016bb-177">Необходимо указать класс, который вы используете:</span><span class="sxs-lookup"><span data-stu-id="016bb-177">You specify the class you're using:</span></span>

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<span data-ttu-id="016bb-178">И теперь можно использовать любой статический метод в классе <xref:System.Math> без уточнения класса <xref:System.Math>.</span><span class="sxs-lookup"><span data-stu-id="016bb-178">And now, you can use any static method in the <xref:System.Math> class without qualifying the <xref:System.Math> class.</span></span> <span data-ttu-id="016bb-179">Класс <xref:System.Math> является отличным примером использования этой функции, так как он не содержит никаких методов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="016bb-179">The <xref:System.Math> class is a great use case for this feature because it does not contain any instance methods.</span></span> <span data-ttu-id="016bb-180">`using static` можно также использовать для импорта статических методов класса для класса, который содержит как статические методы, так и методы экземпляра.</span><span class="sxs-lookup"><span data-stu-id="016bb-180">You can also use `using static` to import a class' static methods for a class that has both static and instance methods.</span></span> <span data-ttu-id="016bb-181">Одним из наиболее полезных примеров является <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="016bb-181">One of the most useful examples is <xref:System.String>:</span></span>

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> <span data-ttu-id="016bb-182">В операторе static using необходимо использовать полное имя класса, `System.String`.</span><span class="sxs-lookup"><span data-stu-id="016bb-182">You must use the fully qualified class name, `System.String` in a static using statement.</span></span> <span data-ttu-id="016bb-183">Нельзя использовать вместо него ключевое слово `string`.</span><span class="sxs-lookup"><span data-stu-id="016bb-183">You cannot use the `string` keyword instead.</span></span> 

<span data-ttu-id="016bb-184">Теперь мы можем вызвать статические методы, определенные в классе <xref:System.String>, без уточнения этих методов как членов данного класса:</span><span class="sxs-lookup"><span data-stu-id="016bb-184">You can now call static methods defined in the <xref:System.String> class without qualifying those methods as members of that class:</span></span>

[!code-csharp[UsingStaticString](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticString)]

<span data-ttu-id="016bb-185">Функция `static using` и методы расширения взаимодействуют интересными способами, и схема языка включает некоторые правила, касающиеся этих взаимодействий.</span><span class="sxs-lookup"><span data-stu-id="016bb-185">The `static using` feature and extension methods interact in interesting ways, and the language design included some rules that specifically address those interactions.</span></span> <span data-ttu-id="016bb-186">Их целью является сведение к минимуму вероятности всех критических изменений в существующих базах кода, включая ваши.</span><span class="sxs-lookup"><span data-stu-id="016bb-186">The goal is to minimize any chances of breaking changes in existing codebases, including yours.</span></span>

<span data-ttu-id="016bb-187">Методы расширения находятся в области только при вызове с помощью синтаксиса вызова метода расширения, но не при вызове в качестве статического метода.</span><span class="sxs-lookup"><span data-stu-id="016bb-187">Extension methods are only in scope when called using the extension method invocation syntax, not when called as a static method.</span></span>
<span data-ttu-id="016bb-188">Это часто встречается в запросах LINQ.</span><span class="sxs-lookup"><span data-stu-id="016bb-188">You'll often see this in LINQ queries.</span></span> <span data-ttu-id="016bb-189">Шаблон LINQ можно импортировать путем импорта <xref:System.Linq.Enumerable>.</span><span class="sxs-lookup"><span data-stu-id="016bb-189">You can import the LINQ pattern by importing <xref:System.Linq.Enumerable>.</span></span>

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

<span data-ttu-id="016bb-190">При этом импортируются все методы в классе <xref:System.Linq.Enumerable>.</span><span class="sxs-lookup"><span data-stu-id="016bb-190">This imports all the methods in the <xref:System.Linq.Enumerable> class.</span></span>
<span data-ttu-id="016bb-191">Однако методы расширения находятся в области только при вызове в качестве методов расширения.</span><span class="sxs-lookup"><span data-stu-id="016bb-191">However, the extension methods are only in scope when called as extension methods.</span></span> <span data-ttu-id="016bb-192">Они не находятся в области, если они вызываются с помощью синтаксиса статического метода:</span><span class="sxs-lookup"><span data-stu-id="016bb-192">They are not in scope if they are called using the static method syntax:</span></span>

[!code-csharp[UsingStaticLinqMethod](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticLinkMethod)]

<span data-ttu-id="016bb-193">Так происходит, поскольку обычно методы расширения вызываются с помощью выражения вызова метода расширения.</span><span class="sxs-lookup"><span data-stu-id="016bb-193">This decision is because extension methods are typically called using extension method invocation expressions.</span></span> <span data-ttu-id="016bb-194">В редких случаях, когда они вызываются с помощью синтаксиса вызова статического метода, это реализуется для устранения неоднозначности.</span><span class="sxs-lookup"><span data-stu-id="016bb-194">In the rare case where they are called using the static method call syntax it is to resolve ambiguity.</span></span>
<span data-ttu-id="016bb-195">Требование имени класса в рамках вызова кажется разумным.</span><span class="sxs-lookup"><span data-stu-id="016bb-195">Requiring the class name as part of the invocation seems wise.</span></span>

<span data-ttu-id="016bb-196">Есть еще одна последняя функция `static using`.</span><span class="sxs-lookup"><span data-stu-id="016bb-196">There's one last feature of `static using`.</span></span> <span data-ttu-id="016bb-197">Директива `static using` также импортирует все вложенные типы.</span><span class="sxs-lookup"><span data-stu-id="016bb-197">The `static using` directive also imports any nested types.</span></span> <span data-ttu-id="016bb-198">Это позволяет ссылаться на любые вложенные типы без указания полного имени.</span><span class="sxs-lookup"><span data-stu-id="016bb-198">That enables you to reference any nested types without qualification.</span></span>

## <a name="null-conditional-operators"></a><span data-ttu-id="016bb-199">Условные операторы NULL</span><span class="sxs-lookup"><span data-stu-id="016bb-199">Null-conditional operators</span></span>

<span data-ttu-id="016bb-200">Значения NULL усложняют код.</span><span class="sxs-lookup"><span data-stu-id="016bb-200">Null values complicate code.</span></span> <span data-ttu-id="016bb-201">Вам приходится проверять каждый случай доступа переменных, чтобы убедиться, что не происходит разыменование `null`.</span><span class="sxs-lookup"><span data-stu-id="016bb-201">You need to check every access of variables to ensure you are not dereferencing `null`.</span></span> <span data-ttu-id="016bb-202">*Условный оператор NULL* существенно упрощает такие проверки.</span><span class="sxs-lookup"><span data-stu-id="016bb-202">The *null conditional operator* makes those checks much easier and fluid.</span></span>

<span data-ttu-id="016bb-203">Просто замените доступ к члену `.` оператором `?.`:</span><span class="sxs-lookup"><span data-stu-id="016bb-203">Simply replace the member access `.` with `?.`:</span></span>

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

<span data-ttu-id="016bb-204">В предыдущем примере переменная `first` назначается `null`, если объект person имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="016bb-204">In the preceding example, the variable `first` is assigned `null` if the person object is `null`.</span></span> <span data-ttu-id="016bb-205">В противном случае назначается значение свойства `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="016bb-205">Otherwise, it gets assigned the value of the `FirstName` property.</span></span> <span data-ttu-id="016bb-206">Важно то, что `?.` означает, что эта строка кода не создает `NullReferenceException`, если переменная `person` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="016bb-206">Most importantly, the `?.` means that this line of code does not generate a `NullReferenceException` when the `person` variable is `null`.</span></span> <span data-ttu-id="016bb-207">Вместо этого выполняется сокращенное вычисление и создание `null`.</span><span class="sxs-lookup"><span data-stu-id="016bb-207">Instead, it short-circuits and produces `null`.</span></span>

<span data-ttu-id="016bb-208">Кроме того, обратите внимание, что это выражение возвращает `string`, независимо от значения `person`.</span><span class="sxs-lookup"><span data-stu-id="016bb-208">Also, note that this expression returns a `string`, regardless of the value of `person`.</span></span>
<span data-ttu-id="016bb-209">В случае сокращенного вычисления возвращаемое значение `null` имеет тип для сопоставления с полным выражением.</span><span class="sxs-lookup"><span data-stu-id="016bb-209">In the case of short circuiting, the `null` value returned is typed to match the full expression.</span></span>

<span data-ttu-id="016bb-210">Эта конструкция часто используется с оператором *объединения со значением NULL* для присвоения значений по умолчанию, если одно из свойств имеет значение `null`:</span><span class="sxs-lookup"><span data-stu-id="016bb-210">You can often use this construct with the *null coalescing* operator to assign default values when one of the properties are `null`:</span></span>

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

<span data-ttu-id="016bb-211">Правый операнд оператора `?.` не ограничивается свойствами или полями.</span><span class="sxs-lookup"><span data-stu-id="016bb-211">The right hand side operand of the `?.` operator is not limited to properties or fields.</span></span>
<span data-ttu-id="016bb-212">Его также можно использовать для условного вызова методов.</span><span class="sxs-lookup"><span data-stu-id="016bb-212">You can also use it to conditionally invoke methods.</span></span> <span data-ttu-id="016bb-213">Чаще всего функции-члены с условным оператором NULL используются для безопасного вызова делегатов (или обработчиков событий), которые могут иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="016bb-213">The most common use of member functions with the null conditional operator is to safely invoke delegates (or event handlers) that may be `null`.</span></span>  <span data-ttu-id="016bb-214">Это реализуется путем вызова метода `Invoke` делегата с помощью оператора `?.` для доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="016bb-214">You'll do this by calling the delegate's `Invoke` method using the `?.` operator to access the member.</span></span> <span data-ttu-id="016bb-215">Пример можно увидеть в разделе, посвященном</span><span class="sxs-lookup"><span data-stu-id="016bb-215">You can see an example in the</span></span>  
<span data-ttu-id="016bb-216">[шаблонам делегатов](../delegates-patterns.md#handling-null-delegates).</span><span class="sxs-lookup"><span data-stu-id="016bb-216">[delegate patterns](../delegates-patterns.md#handling-null-delegates) topic.</span></span>

<span data-ttu-id="016bb-217">Правила оператора `?.` гарантируют, что левая часть оператора вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="016bb-217">The rules of the `?.` operator ensure that the left-hand side of the operator is evaluated only once.</span></span> <span data-ttu-id="016bb-218">Это важно и обеспечивает поддержку многих идиом, включая пример с использованием обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="016bb-218">This is important and enables many idioms, including the example using event handlers.</span></span> <span data-ttu-id="016bb-219">Начнем с использования обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="016bb-219">Let's start with the event handler usage.</span></span> <span data-ttu-id="016bb-220">В предыдущих версиях C# вам рекомендовалось писать код следующим образом:</span><span class="sxs-lookup"><span data-stu-id="016bb-220">In previous versions of C#, you were encouraged to write code like this:</span></span>

```csharp
var handler = this.SomethingHappened;
if (handler != null)
    handler(this, eventArgs);
```

<span data-ttu-id="016bb-221">Это было предпочтительнее, чем упрощенный синтаксис:</span><span class="sxs-lookup"><span data-stu-id="016bb-221">This was preferred over a simpler syntax:</span></span>

```csharp
// Not recommended
if (this.SomethingHappened != null)
    this.SomethingHappened(this, eventArgs);
```

> [!IMPORTANT]
> <span data-ttu-id="016bb-222">Предыдущий пример представляет состояние гонки.</span><span class="sxs-lookup"><span data-stu-id="016bb-222">The preceding example introduces a race condition.</span></span> <span data-ttu-id="016bb-223">Событие `SomethingHappened` может иметь подписчики при проверке на соответствие условию `null`, и эти подписчики могли быть удалены до возникновения события.</span><span class="sxs-lookup"><span data-stu-id="016bb-223">The `SomethingHappened` event may have subscribers when checked against `null`, and those subscribers may have been removed before the event is raised.</span></span> <span data-ttu-id="016bb-224">При этом будет создано исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="016bb-224">That would cause a <xref:System.NullReferenceException> to be thrown.</span></span>

<span data-ttu-id="016bb-225">Во второй версии обработчик событий `SomethingHappened` может не иметь значение NULL при тестировании, но если другой код удаляет обработчик, он может иметь значение NULL при вызове обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="016bb-225">In this second version, the `SomethingHappened` event handler might be non-null when tested, but if other code removes a handler, it could still be null when the event handler was called.</span></span>

<span data-ttu-id="016bb-226">Компилятор создает код для оператора `?.`, который гарантирует, что левая сторона (`this.SomethingHappened`) выражения `?.` вычисляется один раз и результат кэшируется:</span><span class="sxs-lookup"><span data-stu-id="016bb-226">The compiler generates code for the `?.` operator that ensures the left side (`this.SomethingHappened`) of the `?.` expression is evaluated once, and the result is cached:</span></span>

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

<span data-ttu-id="016bb-227">Гарантия того, что левая часть вычисляется только один раз, также позволяет использовать любое выражение, включая вызовы методов, слева от оператора `?.`. Даже если возникнут побочные эффекты, при однократном вычислении они возникнут только один раз.</span><span class="sxs-lookup"><span data-stu-id="016bb-227">Ensuring that the left side is evaluated only once also enables you to use any expression, including method calls, on the left side of the `?.` Even if these have side-effects, they are evaluated once, so the side effects occur only once.</span></span> <span data-ttu-id="016bb-228">Пример можно увидеть в разделе, посвященном [событиям](../events-overview.md#language-support-for-events).</span><span class="sxs-lookup"><span data-stu-id="016bb-228">You can see an example in our content on [events](../events-overview.md#language-support-for-events).</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="016bb-229">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="016bb-229">String Interpolation</span></span>

<span data-ttu-id="016bb-230">C# 6 содержит новый синтаксис для составления строк из строки формата и выражений, которые вычисляются для получения других строковых значений.</span><span class="sxs-lookup"><span data-stu-id="016bb-230">C# 6 contains new syntax for composing strings from a format string and expressions that are evaluated to produce other string values.</span></span>

<span data-ttu-id="016bb-231">Традиционно приходилось использовать позиционные параметры в методе, подобном `string.Format`:</span><span class="sxs-lookup"><span data-stu-id="016bb-231">Traditionally, you needed to use positional parameters in a method like `string.Format`:</span></span>

[!code-csharp[stringFormat](../../../samples/snippets/csharp/new-in-6/oldcode.cs#stringFormat)]

<span data-ttu-id="016bb-232">В C# 6 новая функция [интерполяции строк](../language-reference/tokens/interpolated.md) позволяет внедрить выражения в строку формата.</span><span class="sxs-lookup"><span data-stu-id="016bb-232">With C# 6, the new [string interpolation](../language-reference/tokens/interpolated.md) feature enables you to embed the expressions in the format string.</span></span> <span data-ttu-id="016bb-233">Просто добавьте в строку префикс `$`:</span><span class="sxs-lookup"><span data-stu-id="016bb-233">Simply preface the string with `$`:</span></span>

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="016bb-234">В этом начальном примере для замененных выражений используются выражения свойств.</span><span class="sxs-lookup"><span data-stu-id="016bb-234">This initial example uses property expressions for the substituted expressions.</span></span> <span data-ttu-id="016bb-235">Можно расширить этот синтаксис и использовать любое выражение.</span><span class="sxs-lookup"><span data-stu-id="016bb-235">You can expand on this syntax to use any expression.</span></span> <span data-ttu-id="016bb-236">Например, можно вычислить средний балл учащегося как часть интерполяции:</span><span class="sxs-lookup"><span data-stu-id="016bb-236">For example, you could compute a student's grade point average as part of the interpolation:</span></span>

[!code-csharp[stringInterpolationExpression](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationExpression)]

<span data-ttu-id="016bb-237">Выполняя предыдущий пример, вы могли увидеть, что выходные данные для `Grades.Average()` имеют больше десятичных разрядов, чем хотелось бы.</span><span class="sxs-lookup"><span data-stu-id="016bb-237">Running the preceding example, you would find that the output for `Grades.Average()` might have more decimal places than you would like.</span></span> <span data-ttu-id="016bb-238">Синтаксис интерполяции строк поддерживает все строки формата, доступные с помощью методов форматирования прежних версий.</span><span class="sxs-lookup"><span data-stu-id="016bb-238">The string interpolation syntax supports all the format strings available using earlier formatting methods.</span></span> <span data-ttu-id="016bb-239">Строки формата добавляются внутри фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="016bb-239">You add the format strings inside the braces.</span></span> <span data-ttu-id="016bb-240">Добавьте `:`, за которым следует форматируемое выражение:</span><span class="sxs-lookup"><span data-stu-id="016bb-240">Add a `:` following the expression to format:</span></span>

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

<span data-ttu-id="016bb-241">Предыдущая строка кода форматирует значение для `Grades.Average()` как число с плавающей запятой с двумя десятичными разрядами.</span><span class="sxs-lookup"><span data-stu-id="016bb-241">The preceding line of code formats the value for `Grades.Average()` as a floating-point number with two decimal places.</span></span>

<span data-ttu-id="016bb-242">`:` всегда интерпретируется как разделитель между форматируемым выражением и строкой формата.</span><span class="sxs-lookup"><span data-stu-id="016bb-242">The `:` is always interpreted as the separator between the expression being formatted and the format string.</span></span> <span data-ttu-id="016bb-243">Это может вызвать проблемы, если выражение использует `:` другим способом, например как условный оператор:</span><span class="sxs-lookup"><span data-stu-id="016bb-243">This can introduce problems when your expression uses a `:` in another way, such as a conditional operator:</span></span>

```csharp
public string GetGradePointPercentages() =>
    $"Name: {LastName}, {FirstName}. G.P.A: {Grades.Any() ? Grades.Average() : double.NaN:F2}";
```

<span data-ttu-id="016bb-244">В предыдущем примере `:` анализируется как начало строки формата, а не часть условного оператора.</span><span class="sxs-lookup"><span data-stu-id="016bb-244">In the preceding example, the `:` is parsed as the beginning of the format string, not part of the conditional operator.</span></span> <span data-ttu-id="016bb-245">Во всех случаях, когда это происходит, можно заключить выражение в круглые скобки, чтобы заставить компилятор интерпретировать выражение нужным образом:</span><span class="sxs-lookup"><span data-stu-id="016bb-245">In all cases where this happens, you can surround the expression with parentheses to force the compiler to interpret the expression as you intend:</span></span>

[!code-csharp[stringInterpolationConditional](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationConditional)]

<span data-ttu-id="016bb-246">Нет никаких ограничений на выражения, которые можно поместить в фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="016bb-246">There aren't any limitations on the expressions you can place between the braces.</span></span> <span data-ttu-id="016bb-247">Можно выполнить сложный запрос LINQ внутри интерполированной строки для выполнения вычислений и отображения результата:</span><span class="sxs-lookup"><span data-stu-id="016bb-247">You can execute a complex LINQ query inside an interpolated string to perform computations and display the result:</span></span>

[!code-csharp[stringInterpolationLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationLinq)]

<span data-ttu-id="016bb-248">Из этого примера мы видим, что можно даже вкладывать одно выражение интерполяции строк в другое выражение интерполяции строк.</span><span class="sxs-lookup"><span data-stu-id="016bb-248">You can see from this sample that you can even nest a string interpolation expression inside another string interpolation expression.</span></span> <span data-ttu-id="016bb-249">Этот пример слишком сложный, для того чтобы использовать его в рабочем коде.</span><span class="sxs-lookup"><span data-stu-id="016bb-249">This example is very likely more complex than you would want in production code.</span></span>
<span data-ttu-id="016bb-250">Он приведен, скорее, с целью продемонстрировать широту применения функции.</span><span class="sxs-lookup"><span data-stu-id="016bb-250">Rather, it is illustrative of the breadth of the feature.</span></span> <span data-ttu-id="016bb-251">Любое выражение C# можно поместить между фигурными скобками интерполированной строки.</span><span class="sxs-lookup"><span data-stu-id="016bb-251">Any C# expression can be placed between the curly braces of an interpolated string.</span></span>

### <a name="string-interpolation-and-specific-cultures"></a><span data-ttu-id="016bb-252">Интерполяция строк и конкретные языки и региональные параметры</span><span class="sxs-lookup"><span data-stu-id="016bb-252">String interpolation and specific cultures</span></span>

<span data-ttu-id="016bb-253">Все примеры, приведенные в предыдущем разделе, форматируют строки с использованием текущего языка и региональных параметров на компьютере, где выполняется код.</span><span class="sxs-lookup"><span data-stu-id="016bb-253">All the examples shown in the preceding section format the strings using the current culture and language on the machine where the code executes.</span></span> <span data-ttu-id="016bb-254">Часто требуется отформатировать строку, полученную с использованием конкретного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="016bb-254">Often you may need to format the string produced using a specific culture.</span></span>
<span data-ttu-id="016bb-255">Для этого используйте тот факт, что объект, созданный в результате интерполяции строк, можно неявно преобразовывать в <xref:System.FormattableString>.</span><span class="sxs-lookup"><span data-stu-id="016bb-255">To do that use the fact that the object produced by a string interpolation can be implicitly converted to <xref:System.FormattableString>.</span></span>

<span data-ttu-id="016bb-256">Экземпляр <xref:System.FormattableString> содержит строку формата и результаты вычисления выражений перед их преобразованием в строки.</span><span class="sxs-lookup"><span data-stu-id="016bb-256">The <xref:System.FormattableString> instance contains the format string, and the results of evaluating the expressions before converting them to strings.</span></span> <span data-ttu-id="016bb-257">Вы можете использовать открытые методы <xref:System.FormattableString> для указания языка и региональных параметров при форматировании строки.</span><span class="sxs-lookup"><span data-stu-id="016bb-257">You can use public methods of <xref:System.FormattableString> to specify the culture when formatting a string.</span></span> <span data-ttu-id="016bb-258">Например, приведенный ниже пример создает строку, используя немецкий язык в качестве языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="016bb-258">For example, the following example produces a string using German culture.</span></span> <span data-ttu-id="016bb-259">(В качестве десятичного разделителя используется символ ",", а "." — в качестве разделителя тысяч.)</span><span class="sxs-lookup"><span data-stu-id="016bb-259">(It uses the ',' character for the decimal separator, and the '.' character as the thousands separator.)</span></span>

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

<span data-ttu-id="016bb-260">Дополнительную информацию см. в разделе [Интерполяция строк](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="016bb-260">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span>

## <a name="exception-filters"></a><span data-ttu-id="016bb-261">Фильтры исключений</span><span class="sxs-lookup"><span data-stu-id="016bb-261">Exception Filters</span></span>

<span data-ttu-id="016bb-262">Другая новая функция в C# 6 — *фильтры исключений*.</span><span class="sxs-lookup"><span data-stu-id="016bb-262">Another new feature in C# 6 is *exception filters*.</span></span> <span data-ttu-id="016bb-263">Фильтры исключений — это предложения, которые определяют, когда должно применяться данное предложение catch.</span><span class="sxs-lookup"><span data-stu-id="016bb-263">Exception Filters are clauses that determine when a given catch clause should be applied.</span></span>
<span data-ttu-id="016bb-264">Если выражение, используемое для фильтра исключений, принимает значение `true`, предложение catch выполняет обычную обработку исключения.</span><span class="sxs-lookup"><span data-stu-id="016bb-264">If the expression used for an exception filter evaluates to `true`, the catch clause performs its normal processing on an exception.</span></span> <span data-ttu-id="016bb-265">Если выражение принимает значение `false`, то предложение `catch` пропускается.</span><span class="sxs-lookup"><span data-stu-id="016bb-265">If the expression evaluates to `false`, then the `catch` clause is skipped.</span></span>

<span data-ttu-id="016bb-266">Например, эту функцию можно использовать для просмотра сведений об исключении, чтобы определить, может ли предложение `catch` обработать исключение:</span><span class="sxs-lookup"><span data-stu-id="016bb-266">One use is to examine information about an exception to determine if a `catch` clause can process the exception:</span></span>

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

<span data-ttu-id="016bb-267">Код, созданный фильтрами исключений, предоставляет больше информации об исключении, которое создано и не обработано.</span><span class="sxs-lookup"><span data-stu-id="016bb-267">The code generated by exception filters provides better information about an exception that is thrown and not processed.</span></span> <span data-ttu-id="016bb-268">До добавления фильтров исключений в язык приходилось создавать код, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="016bb-268">Before exception filters were added to the language, you would need to create code like the following:</span></span>

[!code-csharp[ExceptionFilterOld](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilterOld)]

<span data-ttu-id="016bb-269">Точка, где создается исключение, неодинакова в этих двух примерах.</span><span class="sxs-lookup"><span data-stu-id="016bb-269">The point where the exception is thrown changes between these two examples.</span></span>
<span data-ttu-id="016bb-270">В предыдущем коде, где используется предложение `throw`, любой анализ трассировки стека или анализ аварийных дампов выведет только то исключение, которое было вызвано из оператора `throw` в предложении catch.</span><span class="sxs-lookup"><span data-stu-id="016bb-270">In the previous code, where a `throw` clause is used, any stack trace analysis or examination of crash dumps will show that the exception was thrown from the `throw` statement in your catch clause.</span></span> <span data-ttu-id="016bb-271">Фактический объект исключения будет содержать исходный стек вызовов, однако все остальные сведения обо всех переменных в стеке вызовов между этой точкой создания исключения и расположением исходной точки создания исключения будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="016bb-271">The actual exception object will contain the original call stack, but all other information about any variables in the call stack between this throw point and the location of the original throw point has been lost.</span></span> 

<span data-ttu-id="016bb-272">Сравните это с обработкой кода, использующего фильтр исключений: выражение фильтра исключений принимает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="016bb-272">Contrast that with how the code using an exception filter is processed: the exception filter expression evaluates to `false`.</span></span> <span data-ttu-id="016bb-273">Таким образом, выполнение никогда не входит в предложение `catch`.</span><span class="sxs-lookup"><span data-stu-id="016bb-273">Therefore, execution never enters the `catch` clause.</span></span> <span data-ttu-id="016bb-274">Поскольку предложение `catch` не выполняется, развертывание стека не происходит.</span><span class="sxs-lookup"><span data-stu-id="016bb-274">Because the `catch` clause does not execute, no stack unwinding takes place.</span></span> <span data-ttu-id="016bb-275">Это означает, что исходное расположение исключения сохраняется для любых действий отладки, которые будет выполняться позже.</span><span class="sxs-lookup"><span data-stu-id="016bb-275">That means the original throw location is preserved for any debugging activities that would take place later.</span></span>

<span data-ttu-id="016bb-276">Для обработки полей или свойств исключения, не полагаясь исключительно на тип исключения, используйте фильтр исключений для сохранения дополнительных отладочных сведений.</span><span class="sxs-lookup"><span data-stu-id="016bb-276">Whenever you need to evaluate fields or properties of an exception, instead of relying solely on the exception type, use an exception filter to preserve more debugging information.</span></span>

<span data-ttu-id="016bb-277">Другим рекомендуемым примером применения фильтров исключений является их использование для операций ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="016bb-277">Another recommended pattern with exception filters is to use them for logging routines.</span></span> <span data-ttu-id="016bb-278">В этом случае также используется подход, в котором точка создания исключения сохраняется, если фильтр исключений принимает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="016bb-278">This usage also leverages the manner in which the exception throw point is preserved when an exception filter evaluates to `false`.</span></span>

<span data-ttu-id="016bb-279">Методом ведения журнала будет метод, аргументом которого является исключение, безусловно возвращающее `false`:</span><span class="sxs-lookup"><span data-stu-id="016bb-279">A logging method would be a method whose argument is the exception that unconditionally returns `false`:</span></span>

[!code-csharp[ExceptionFilterLogging](../../../samples/snippets/csharp/new-in-6/ExceptionFilterHelpers.cs#ExceptionFilterLogging)]

<span data-ttu-id="016bb-280">Каждый раз, когда требуется записать исключение в журнал, можно добавить предложение catch и использовать этот метод в качестве фильтра исключений:</span><span class="sxs-lookup"><span data-stu-id="016bb-280">Whenever you want to log an exception, you can add a catch clause, and use this method as the exception filter:</span></span>

[!code-csharp[LogException](../../../samples/snippets/csharp/new-in-6/program.cs#LogException)]

<span data-ttu-id="016bb-281">Исключения никогда не перехватываются, так как метод `LogException` всегда возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="016bb-281">The exceptions are never caught, because the `LogException` method always returns `false`.</span></span> <span data-ttu-id="016bb-282">Такой фильтр исключений, всегда имеющий значение false, означает, что вы можете поместить этот обработчик ведения журнала перед любым другим обработчиком исключений:</span><span class="sxs-lookup"><span data-stu-id="016bb-282">That always false exception filter means that you can place this logging handler before any other exception handlers:</span></span>

[!code-csharp[LogExceptionRecovery](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionRecovery)]

<span data-ttu-id="016bb-283">Предыдущий пример демонстрирует очень важный аспект фильтров исключений.</span><span class="sxs-lookup"><span data-stu-id="016bb-283">The preceding example highlights a very important facet of exception filters.</span></span>
<span data-ttu-id="016bb-284">Фильтры исключений поддерживают сценарии, в которых более общие предложения перехвата исключений могут предшествовать более конкретным предложениям.</span><span class="sxs-lookup"><span data-stu-id="016bb-284">The exception filters enable scenarios where a more general exception catch clause may appear before a more specific one.</span></span> <span data-ttu-id="016bb-285">Кроме того, один тип исключения может появляться в нескольких предложениях catch:</span><span class="sxs-lookup"><span data-stu-id="016bb-285">It's also possible to have the same exception type appear in multiple catch clauses:</span></span>

[!code-csharp[HandleNotChanged](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#HandleNotChanged)]

<span data-ttu-id="016bb-286">Другой рекомендуемый способ использования помогает предотвратить обработку предложениями catch исключений, если подключен отладчик.</span><span class="sxs-lookup"><span data-stu-id="016bb-286">Another recommended pattern helps prevent catch clauses from processing exceptions when a debugger is attached.</span></span> <span data-ttu-id="016bb-287">Этот метод позволяет запускать приложения с помощью отладчика и останавливать выполнение при возникновении исключения.</span><span class="sxs-lookup"><span data-stu-id="016bb-287">This technique enables you to run an application with the debugger, and stop execution when an exception is thrown.</span></span>

<span data-ttu-id="016bb-288">Добавьте в свой код фильтр исключений, чтобы любой код восстановления выполнялся только в том случае, если отладчик не подключен:</span><span class="sxs-lookup"><span data-stu-id="016bb-288">In your code, add an exception filter so that any recovery code executes only when a debugger is not attached:</span></span>

[!code-csharp[LogExceptionDebugger](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionDebugger)]

<span data-ttu-id="016bb-289">После добавления этого кода задайте для отладчика прерывание по всем необработанным исключениям.</span><span class="sxs-lookup"><span data-stu-id="016bb-289">After adding this in code, you set your debugger to break on all unhandled exceptions.</span></span> <span data-ttu-id="016bb-290">Запустите программу в отладчике, и отладчик будет прерывать выполнение при каждом вызове `PerformFailingOperation()` исключения `RecoverableException`.</span><span class="sxs-lookup"><span data-stu-id="016bb-290">Run the program under the debugger, and the debugger breaks whenever `PerformFailingOperation()` throws a `RecoverableException`.</span></span>
<span data-ttu-id="016bb-291">Отладчик прерывает выполнение программы, так как предложение catch не выполняется из-за фильтра исключения, возвращающего значение false.</span><span class="sxs-lookup"><span data-stu-id="016bb-291">The debugger breaks your program, because the catch clause won't be executed due to the false-returning exception filter.</span></span>

## <a name="nameof-expressions"></a><span data-ttu-id="016bb-292">Выражения `nameof`</span><span class="sxs-lookup"><span data-stu-id="016bb-292">`nameof` Expressions</span></span>

<span data-ttu-id="016bb-293">Результатом выражения `nameof` является имя символа.</span><span class="sxs-lookup"><span data-stu-id="016bb-293">The `nameof` expression evaluates to the name of a symbol.</span></span> <span data-ttu-id="016bb-294">Это отличный способ заставить инструменты работать, если вам требуется имя переменной, свойства или поля члена.</span><span class="sxs-lookup"><span data-stu-id="016bb-294">It's a great way to get tools working whenever you need the name of a variable, a property, or a member field.</span></span>

<span data-ttu-id="016bb-295">Одно из наиболее распространенных применений `nameof` — предоставление имени символа, который вызвал исключение:</span><span class="sxs-lookup"><span data-stu-id="016bb-295">One of the most common uses for `nameof` is to provide the name of a symbol that caused an exception:</span></span>

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

<span data-ttu-id="016bb-296">Другая сфера применения — с приложениями на основе XAML, реализующими интерфейс `INotifyPropertyChanged`:</span><span class="sxs-lookup"><span data-stu-id="016bb-296">Another use is with XAML based applications that implement the `INotifyPropertyChanged` interface:</span></span>

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

<span data-ttu-id="016bb-297">Преимущество использования оператора `nameof` по сравнению со строковой константой заключается в том, что инструменты могут распознать символ.</span><span class="sxs-lookup"><span data-stu-id="016bb-297">The advantage of using the `nameof` operator over a constant string is that tools can understand the symbol.</span></span> <span data-ttu-id="016bb-298">При использовании инструментов рефакторинга для переименования символа он будет переименован в выражение `nameof`.</span><span class="sxs-lookup"><span data-stu-id="016bb-298">If you use refactoring tools to rename the symbol, it will rename it in the `nameof` expression.</span></span> <span data-ttu-id="016bb-299">Константные строки не обеспечивают такого преимущества.</span><span class="sxs-lookup"><span data-stu-id="016bb-299">Constant strings don't have that advantage.</span></span> <span data-ttu-id="016bb-300">Попробуйте сделать это в своем любимом редакторе: переименуйте переменную, и все выражения `nameof` также обновятся.</span><span class="sxs-lookup"><span data-stu-id="016bb-300">Try it yourself in your favorite editor: rename a variable, and any `nameof` expressions will update as well.</span></span>

<span data-ttu-id="016bb-301">Выражение `nameof` создает неполное имя своего аргумента (`LastName` в предыдущих примерах) даже при использовании для аргумента полного имени:</span><span class="sxs-lookup"><span data-stu-id="016bb-301">The `nameof` expression produces the unqualified name of its argument (`LastName` in the previous examples) even if you use the fully qualified name for the argument:</span></span>

[!code-csharp[QualifiedNameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#QualifiedNameofNotify)]

<span data-ttu-id="016bb-302">Это выражение `nameof` создает `FirstName`, а не `UXComponents.ViewModel.FirstName`.</span><span class="sxs-lookup"><span data-stu-id="016bb-302">This `nameof` expression produces `FirstName`, not `UXComponents.ViewModel.FirstName`.</span></span>

## <a name="await-in-catch-and-finally-blocks"></a><span data-ttu-id="016bb-303">Выражение Await в блоках Catch и Finally</span><span class="sxs-lookup"><span data-stu-id="016bb-303">Await in Catch and Finally blocks</span></span>

<span data-ttu-id="016bb-304">В C# 5 было несколько ограничений в отношении размещения выражений `await`.</span><span class="sxs-lookup"><span data-stu-id="016bb-304">C# 5 had several limitations around where you could place `await` expressions.</span></span>
<span data-ttu-id="016bb-305">Одно из них удалено в C# 6.</span><span class="sxs-lookup"><span data-stu-id="016bb-305">One of those has been removed in C# 6.</span></span> <span data-ttu-id="016bb-306">Теперь вы можете использовать `await` в выражениях `catch` или `finally`.</span><span class="sxs-lookup"><span data-stu-id="016bb-306">You can now use `await` in `catch` or `finally` expressions.</span></span> 

<span data-ttu-id="016bb-307">Может показаться, что добавление выражений await в блоки catch и finally усложняет их обработку.</span><span class="sxs-lookup"><span data-stu-id="016bb-307">The addition of await expressions in catch and finally blocks may appear to complicate how those are processed.</span></span> <span data-ttu-id="016bb-308">Добавим пример, чтобы рассмотреть этот случай.</span><span class="sxs-lookup"><span data-stu-id="016bb-308">Let's add an example to discuss how this appears.</span></span> <span data-ttu-id="016bb-309">В любом асинхронном методе можно использовать выражение await в предложении finally.</span><span class="sxs-lookup"><span data-stu-id="016bb-309">In any async method, you can use an await expression in a finally clause.</span></span>

<span data-ttu-id="016bb-310">В C# 6 ожидание также может выполняться в выражениях catch.</span><span class="sxs-lookup"><span data-stu-id="016bb-310">With C# 6, you can also await in catch expressions.</span></span> <span data-ttu-id="016bb-311">Чаще всего это используется в сценариях ведения журнала:</span><span class="sxs-lookup"><span data-stu-id="016bb-311">This is most often used with logging scenarios:</span></span>

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

<span data-ttu-id="016bb-312">Реализация добавления поддержки `await` внутри предложений `catch` и `finally` гарантирует согласованность поведения с поведением для синхронного кода.</span><span class="sxs-lookup"><span data-stu-id="016bb-312">The implementation details for adding `await` support inside `catch` and `finally` clauses ensures that the behavior is consistent with the behavior for synchronous code.</span></span> <span data-ttu-id="016bb-313">Если код, выполняемый в предложении `catch` или `finally`, создает исключение, выполнение ищет подходящее предложение `catch` в следующем окружающем блоке.</span><span class="sxs-lookup"><span data-stu-id="016bb-313">When code executed in a `catch` or `finally` clause throws, execution looks for a suitable `catch` clause in the next surrounding block.</span></span> <span data-ttu-id="016bb-314">При наличии текущего исключения это исключение будет потеряно.</span><span class="sxs-lookup"><span data-stu-id="016bb-314">If there was a current exception, that exception is lost.</span></span> <span data-ttu-id="016bb-315">То же самое происходит с ожидаемыми выражениями в предложениях `catch` и `finally`: выполняется поиск подходящего `catch`, а текущее исключение (при наличии) утрачивается.</span><span class="sxs-lookup"><span data-stu-id="016bb-315">The same happens with awaited expressions in `catch` and `finally` clauses: a suitable `catch` is searched for, and the current exception, if any, is lost.</span></span>  

> [!NOTE]
> <span data-ttu-id="016bb-316">Это поведение лежит в основе рекомендации тщательного написания предложений `catch` и `finally` во избежание внесения новых исключений.</span><span class="sxs-lookup"><span data-stu-id="016bb-316">This behavior is the reason it's recommended to write `catch` and `finally` clauses carefully, to avoid introducing new exceptions.</span></span>

## <a name="index-initializers"></a><span data-ttu-id="016bb-317">См. раздел Инициализаторы индекса.</span><span class="sxs-lookup"><span data-stu-id="016bb-317">Index Initializers</span></span>

<span data-ttu-id="016bb-318">*Инициализаторы индекса* — это одна из двух функций, обеспечивающих согласованность инициализаторов коллекций.</span><span class="sxs-lookup"><span data-stu-id="016bb-318">*Index Initializers* is one of two features that make collection initializers more consistent.</span></span> <span data-ttu-id="016bb-319">В более ранних версиях C# можно было использовать *инициализаторы коллекций* только с коллекциями типа последовательности:</span><span class="sxs-lookup"><span data-stu-id="016bb-319">In earlier releases of C#, you could use *collection initializers* only with sequence style collections:</span></span>

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#ListInitializer)]

<span data-ttu-id="016bb-320">Теперь их можно также использовать с коллекциями <xref:System.Collections.Generic.Dictionary%602> и других аналогичных типов:</span><span class="sxs-lookup"><span data-stu-id="016bb-320">Now, you can also use them with <xref:System.Collections.Generic.Dictionary%602> collections and similar types:</span></span>

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

<span data-ttu-id="016bb-321">Эта функция означает, что ассоциативные контейнеры могут быть инициализированы с помощью синтаксиса, аналогичного используемому для контейнеров последовательностей для нескольких версий.</span><span class="sxs-lookup"><span data-stu-id="016bb-321">This feature means that associative containers can be initialized using syntax similar to what's been in place for sequence containers for several versions.</span></span>

### <a name="extension-add-methods-in-collection-initializers"></a><span data-ttu-id="016bb-322">Методы расширения `Add` в инициализаторах коллекций</span><span class="sxs-lookup"><span data-stu-id="016bb-322">Extension `Add` methods in collection initializers</span></span>

<span data-ttu-id="016bb-323">Еще одна функция, упрощающая инициализацию коллекций, — это возможность использования *метода расширения* для метода `Add`.</span><span class="sxs-lookup"><span data-stu-id="016bb-323">Another feature that makes collection initialization easier is the ability to use an *extension method* for the `Add` method.</span></span> <span data-ttu-id="016bb-324">Эта функция была добавлена для согласования с Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="016bb-324">This feature was added for parity with Visual Basic.</span></span> 

<span data-ttu-id="016bb-325">Она наиболее удобна при наличии пользовательского класса коллекции, имеющего метод с другим именем для семантического добавления новых элементов.</span><span class="sxs-lookup"><span data-stu-id="016bb-325">The feature is most useful when you have a custom collection class that has a method with a different name to semantically add new items.</span></span>

<span data-ttu-id="016bb-326">Например, рассмотрим коллекцию учащихся:</span><span class="sxs-lookup"><span data-stu-id="016bb-326">For example, consider a collection of students like this:</span></span>

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]

<span data-ttu-id="016bb-327">Метод `Enroll` добавляет учащихся.</span><span class="sxs-lookup"><span data-stu-id="016bb-327">The `Enroll` method adds a student.</span></span> <span data-ttu-id="016bb-328">Однако он не соответствует шаблону `Add`.</span><span class="sxs-lookup"><span data-stu-id="016bb-328">But it doesn't follow the `Add` pattern.</span></span>
<span data-ttu-id="016bb-329">В предыдущих версиях C# нельзя было использовать инициализаторы коллекций с объектом `Enrollment`:</span><span class="sxs-lookup"><span data-stu-id="016bb-329">In previous versions of C#, you could not use collection initializers with an `Enrollment` object:</span></span>

[!code-csharp[InitializeEnrollment](../../../samples/snippets/csharp/new-in-6/classList.cs#InitializeEnrollment)]

<span data-ttu-id="016bb-330">Теперь вы можете это сделать, но только в том случае, если создадите метод расширения, который сопоставляет `Add` с `Enroll`:</span><span class="sxs-lookup"><span data-stu-id="016bb-330">Now you can, but only if you create an extension method that maps `Add` to `Enroll`:</span></span>

[!code-csharp[ExtensionAdd](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAdd)]

<span data-ttu-id="016bb-331">Эта функция сопоставляет любой метод, который добавляет элементы в коллекцию, с методом `Add` путем создания метода расширения:</span><span class="sxs-lookup"><span data-stu-id="016bb-331">What you are doing with this feature is to map whatever method adds items to a collection to a method named `Add` by creating an extension method:</span></span> 

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]
[!code-csharp[ExtensionAddSample](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAddSample)]

## <a name="improved-overload-resolution"></a><span data-ttu-id="016bb-332">Улучшенное разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="016bb-332">Improved overload resolution</span></span>

<span data-ttu-id="016bb-333">Эта последняя функция, на которую вы, вероятно, не обратите внимания.</span><span class="sxs-lookup"><span data-stu-id="016bb-333">This last feature is one you probably won't notice.</span></span> <span data-ttu-id="016bb-334">Есть примеры того, что предыдущая версия компилятора C# могла определять некоторые вызовы методов, работающих с лямбда-выражениями, как неоднозначные.</span><span class="sxs-lookup"><span data-stu-id="016bb-334">There were constructs where the previous version of the C# compiler may have found some method calls involving lambda expressions ambiguous.</span></span> <span data-ttu-id="016bb-335">Рассмотрим этот метод:</span><span class="sxs-lookup"><span data-stu-id="016bb-335">Consider this method:</span></span>

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

<span data-ttu-id="016bb-336">В более ранних версиях C# вызов этого метода с использованием синтаксиса группы методов приведет к сбою:</span><span class="sxs-lookup"><span data-stu-id="016bb-336">In earlier versions of C#, calling that method using the method group syntax would fail:</span></span>

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]
 
<span data-ttu-id="016bb-337">Компилятор прежних версий не мог правильно различать методы `Task.Run(Action)` и `Task.Run(Func<Task>())`.</span><span class="sxs-lookup"><span data-stu-id="016bb-337">The earlier compiler could not distinguish correctly between `Task.Run(Action)` and `Task.Run(Func<Task>())`.</span></span> <span data-ttu-id="016bb-338">В предыдущих версиях вам бы потребовалось использовать лямбда-выражение в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="016bb-338">In previous versions, you'd need to use a lambda expression as an argument:</span></span>

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

<span data-ttu-id="016bb-339">Компилятор C# 6 правильно определяет, что `Task.Run(Func<Task>())` является лучшим вариантом.</span><span class="sxs-lookup"><span data-stu-id="016bb-339">The C# 6 compiler correctly determines that `Task.Run(Func<Task>())` is a better choice.</span></span>
