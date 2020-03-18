---
title: Новые возможности C# 6. Руководство по языку C#
description: Сведения о новых возможностях в C# 6
ms.date: 12/12/2018
ms.openlocfilehash: da40b4c9d4af0094fdd907c542e971ba55086e0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398157"
---
# <a name="whats-new-in-c-6"></a><span data-ttu-id="fd268-103">Новые возможности C# 6</span><span class="sxs-lookup"><span data-stu-id="fd268-103">What's New in C# 6</span></span>

<span data-ttu-id="fd268-104">Версия C# 6.0 содержит множество функций, помогающих повысить производительность труда разработчиков.</span><span class="sxs-lookup"><span data-stu-id="fd268-104">The 6.0 release of C# contained many features that improve productivity for developers.</span></span> <span data-ttu-id="fd268-105">Общим эффектом этих функций является написание более краткого кода, который также является более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="fd268-105">The overall effect of these features is that you write more concise code that is also more readable.</span></span> <span data-ttu-id="fd268-106">Синтаксис содержит меньше формальных элементов для многих общих рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="fd268-106">The syntax contains less ceremony for many common practices.</span></span> <span data-ttu-id="fd268-107">Благодаря краткости становится проще понять назначение кода.</span><span class="sxs-lookup"><span data-stu-id="fd268-107">It's easier to see the design intent with less ceremony.</span></span> <span data-ttu-id="fd268-108">Хорошо изучив эти возможности, вы сможете работать более производительно и создавать более читаемый код.</span><span class="sxs-lookup"><span data-stu-id="fd268-108">Learn these features well, and you'll be more productive and write more readable code.</span></span> <span data-ttu-id="fd268-109">Вы можете посвятить больше времени разработке вашей функциональности, а не конструкциям языка.</span><span class="sxs-lookup"><span data-stu-id="fd268-109">You can concentrate more on your features than on the constructs of the language.</span></span>

<span data-ttu-id="fd268-110">В оставшейся части этой статьи приведены общие сведения о каждой из этих функций со ссылкой для изучения каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="fd268-110">The rest of this article provides an overview of each of these features, with a link to explore each feature.</span></span> <span data-ttu-id="fd268-111">Вы также можете ознакомиться с функциями в [интерактивном обзоре по C# 6](../tutorials/exploration/csharp-6.yml) в разделе учебников.</span><span class="sxs-lookup"><span data-stu-id="fd268-111">You can also explore the features in an [interactive exploration on C# 6](../tutorials/exploration/csharp-6.yml) in the tutorials section.</span></span>

## <a name="read-only-auto-properties"></a><span data-ttu-id="fd268-112">Автосвойства, доступные только для чтения</span><span class="sxs-lookup"><span data-stu-id="fd268-112">Read-only auto-properties</span></span>

<span data-ttu-id="fd268-113">*Автосвойства только для чтения* предоставляют более краткий синтаксис для создания неизменяемых типов.</span><span class="sxs-lookup"><span data-stu-id="fd268-113">*Read-only auto-properties* provide a more concise syntax to create immutable types.</span></span> <span data-ttu-id="fd268-114">Автосвойство объявляется с помощью только метода доступа get:</span><span class="sxs-lookup"><span data-stu-id="fd268-114">You declare the auto-property with only a get accessor:</span></span>

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

<span data-ttu-id="fd268-115">Свойства `FirstName` и `LastName` могут задаваться только в теле конструктора того же класса:</span><span class="sxs-lookup"><span data-stu-id="fd268-115">The `FirstName` and `LastName` properties can be set only in the body of the constructor of the same class:</span></span>

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

<span data-ttu-id="fd268-116">Попытка задать `LastName` в другом методе создает ошибку компиляции `CS0200`:</span><span class="sxs-lookup"><span data-stu-id="fd268-116">Trying to set `LastName` in another method generates a `CS0200` compilation error:</span></span>

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

<span data-ttu-id="fd268-117">Эта функция обеспечивает действительную поддержку создания неизменяемых типов на уровне языка и использование более краткого и удобного синтаксиса автосвойств.</span><span class="sxs-lookup"><span data-stu-id="fd268-117">This feature enables true language support for creating immutable types and uses the more concise and convenient auto-property syntax.</span></span>

<span data-ttu-id="fd268-118">Если в результате добавления такого синтаксиса доступный метод не удаляется, такое изменение считается [совместимым на уровне двоичного кода](version-update-considerations.md#binary-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="fd268-118">If adding this syntax doesn't remove an accessible method, it's a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="auto-property-initializers"></a><span data-ttu-id="fd268-119">Инициализаторы автосвойств</span><span class="sxs-lookup"><span data-stu-id="fd268-119">Auto-property initializers</span></span>

<span data-ttu-id="fd268-120">*Инициализаторы автосвойств* позволяют объявить начальное значение для автосвойства при объявлении свойства.</span><span class="sxs-lookup"><span data-stu-id="fd268-120">*Auto-property initializers* let you declare the initial value for an auto-property as part of the property declaration.</span></span>

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

<span data-ttu-id="fd268-121">Член `Grades` инициализируется там, где он объявлен.</span><span class="sxs-lookup"><span data-stu-id="fd268-121">The `Grades` member is initialized where it's declared.</span></span> <span data-ttu-id="fd268-122">Это упрощает выполнение инициализации ровно один раз.</span><span class="sxs-lookup"><span data-stu-id="fd268-122">That makes it easier to perform the initialization exactly once.</span></span> <span data-ttu-id="fd268-123">Инициализация является частью объявления свойства, упрощая уравнение выделения хранилища с открытым интерфейсом для объектов `Student`.</span><span class="sxs-lookup"><span data-stu-id="fd268-123">The initialization is part of the property declaration, making it easier to equate the storage allocation with the public interface for `Student` objects.</span></span>

## <a name="expression-bodied-function-members"></a><span data-ttu-id="fd268-124">Члены функции, воплощающие выражение</span><span class="sxs-lookup"><span data-stu-id="fd268-124">Expression-bodied function members</span></span>

<span data-ttu-id="fd268-125">Большое количество элементов, которые вы пишете, будут выражены одиночной инструкцией и могут быть отдельными выражениями.</span><span class="sxs-lookup"><span data-stu-id="fd268-125">Many members that you write are single statements that could be single expressions.</span></span> <span data-ttu-id="fd268-126">Вместо этого напишите элемент с телом выражения.</span><span class="sxs-lookup"><span data-stu-id="fd268-126">Write an expression-bodied member instead.</span></span> <span data-ttu-id="fd268-127">Это работает для методов и свойств, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="fd268-127">It works for methods and read-only properties.</span></span> <span data-ttu-id="fd268-128">Например, переопределение `ToString()` часто бывает отличным кандидатом:</span><span class="sxs-lookup"><span data-stu-id="fd268-128">For example, an override of `ToString()` is often a great candidate:</span></span>

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

<span data-ttu-id="fd268-129">Этот синтаксис также можно использовать для свойств только для чтения:</span><span class="sxs-lookup"><span data-stu-id="fd268-129">You can also use this syntax for read-only properties:</span></span>

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="fd268-130">Изменение существующего члена, воплощающего выражение, является [двоично совместимым изменением](version-update-considerations.md#binary-compatible-changes).</span><span class="sxs-lookup"><span data-stu-id="fd268-130">Changing an existing member to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="using-static"></a><span data-ttu-id="fd268-131">using static</span><span class="sxs-lookup"><span data-stu-id="fd268-131">using static</span></span>

<span data-ttu-id="fd268-132">Усовершенствование *using static* позволяет импортировать статические методы одного класса.</span><span class="sxs-lookup"><span data-stu-id="fd268-132">The *using static* enhancement enables you to import the static methods of a single class.</span></span> <span data-ttu-id="fd268-133">Необходимо указать класс, который вы используете:</span><span class="sxs-lookup"><span data-stu-id="fd268-133">You specify the class you're using:</span></span>

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<span data-ttu-id="fd268-134">Объект <xref:System.Math> не содержит никаких элементов экземпляров.</span><span class="sxs-lookup"><span data-stu-id="fd268-134">The <xref:System.Math> does not contain any instance methods.</span></span> <span data-ttu-id="fd268-135">`using static` можно также использовать для импорта статических методов класса для класса, который содержит как статические методы, так и методы экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fd268-135">You can also use `using static` to import a class' static methods for a class that has both static and instance methods.</span></span> <span data-ttu-id="fd268-136">Одним из наиболее полезных примеров является <xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="fd268-136">One of the most useful examples is <xref:System.String>:</span></span>

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> <span data-ttu-id="fd268-137">В операторе static using необходимо использовать полное имя класса, `System.String`.</span><span class="sxs-lookup"><span data-stu-id="fd268-137">You must use the fully qualified class name, `System.String`  in a static using statement.</span></span>  <span data-ttu-id="fd268-138">Нельзя использовать вместо него ключевое слово `string`.</span><span class="sxs-lookup"><span data-stu-id="fd268-138">You cannot use the `string` keyword instead.</span></span>

<span data-ttu-id="fd268-139">При импорте из оператора `static using` методы расширения находятся в области только при вызове с помощью синтаксиса вызова метода расширения.</span><span class="sxs-lookup"><span data-stu-id="fd268-139">When imported from a `static using` statement, extension methods are only in scope when called using the extension method invocation syntax.</span></span> <span data-ttu-id="fd268-140">Это не так при вызове в качестве статического метода.</span><span class="sxs-lookup"><span data-stu-id="fd268-140">They aren't in scope when called as a static method.</span></span> <span data-ttu-id="fd268-141">Это часто встречается в запросах LINQ.</span><span class="sxs-lookup"><span data-stu-id="fd268-141">You'll often see this in LINQ queries.</span></span> <span data-ttu-id="fd268-142">Шаблон LINQ можно импортировать путем импорта <xref:System.Linq.Enumerable> или <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="fd268-142">You can import the LINQ pattern by importing <xref:System.Linq.Enumerable>, or <xref:System.Linq.Queryable>.</span></span>

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

<span data-ttu-id="fd268-143">Обычно методы расширения вызываются с помощью выражения вызова метода расширения.</span><span class="sxs-lookup"><span data-stu-id="fd268-143">You typically call extension methods using extension method invocation expressions.</span></span> <span data-ttu-id="fd268-144">Добавление имени класса в тех редких случаях, где их можно вызывать с помощью вызова статического метода, устраняет неоднозначность.</span><span class="sxs-lookup"><span data-stu-id="fd268-144">Adding the class name in the rare case where you call them using static method call syntax resolves ambiguity.</span></span>

<span data-ttu-id="fd268-145">Директива `static using` также импортирует все вложенные типы.</span><span class="sxs-lookup"><span data-stu-id="fd268-145">The `static using` directive also imports any nested types.</span></span> <span data-ttu-id="fd268-146">Вы можете ссылаться на любые вложенные типы без указания полного имени.</span><span class="sxs-lookup"><span data-stu-id="fd268-146">You can reference any nested types without qualification.</span></span>

## <a name="null-conditional-operators"></a><span data-ttu-id="fd268-147">Условные операторы NULL</span><span class="sxs-lookup"><span data-stu-id="fd268-147">Null-conditional operators</span></span>

<span data-ttu-id="fd268-148">*Условный оператор NULL* существенно упрощает проверки на NULL.</span><span class="sxs-lookup"><span data-stu-id="fd268-148">The *null conditional operator* makes null checks much easier and fluid.</span></span> <span data-ttu-id="fd268-149">Замените доступ к члену `.` оператором `?.`:</span><span class="sxs-lookup"><span data-stu-id="fd268-149">Replace the member access `.` with `?.`:</span></span>

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

<span data-ttu-id="fd268-150">В предыдущем примере переменная `first` назначается `null`, если объект person имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="fd268-150">In the preceding example, the variable `first` is assigned `null` if the person object is `null`.</span></span> <span data-ttu-id="fd268-151">В противном случае назначается значение свойства `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="fd268-151">Otherwise, it is assigned the value of the `FirstName` property.</span></span> <span data-ttu-id="fd268-152">Важно то, что `?.` означает, что эта строка кода не создает `NullReferenceException`, если переменная `person` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="fd268-152">Most importantly, the `?.` means that this line of code doesn't generate a `NullReferenceException` if the `person` variable is `null`.</span></span> <span data-ttu-id="fd268-153">Вместо этого выполняется сокращенное вычисление, и возвращается `null`.</span><span class="sxs-lookup"><span data-stu-id="fd268-153">Instead, it short-circuits and returns `null`.</span></span> <span data-ttu-id="fd268-154">Можно также использовать условный оператор NULL для доступа к массиву или индексатору.</span><span class="sxs-lookup"><span data-stu-id="fd268-154">You can also use a null conditional operator for array or indexer access.</span></span> <span data-ttu-id="fd268-155">Замените `[]` на `?[]` в выражении индекса.</span><span class="sxs-lookup"><span data-stu-id="fd268-155">Replace `[]` with `?[]` in the index expression.</span></span>

<span data-ttu-id="fd268-156">Следующее выражение возвращает `string`, независимо от значения `person`.</span><span class="sxs-lookup"><span data-stu-id="fd268-156">The following expression returns a `string`, regardless of the value of `person`.</span></span> <span data-ttu-id="fd268-157">Эта конструкция часто используется с оператором *объединения со значением NULL* для присвоения значений по умолчанию, если одно из свойств имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="fd268-157">You often use this construct with the *null coalescing* operator to assign default values when one of the properties is `null`.</span></span> <span data-ttu-id="fd268-158">В случае сокращенного вычисления выражений возвращаемое значение `null` имеет тип для сопоставления с полным выражением.</span><span class="sxs-lookup"><span data-stu-id="fd268-158">When the expression short-circuits, the `null` value returned is typed to match the full expression.</span></span>

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

<span data-ttu-id="fd268-159">`?.` также можно использовать для условного вызова методов.</span><span class="sxs-lookup"><span data-stu-id="fd268-159">You can also use `?.` to conditionally invoke methods.</span></span> <span data-ttu-id="fd268-160">Чаще всего функции-члены с условным оператором NULL используются для безопасного вызова делегатов (или обработчиков событий), которые могут иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="fd268-160">The most common use of member functions  with the null conditional operator is to safely invoke delegates (or event handlers) that may be `null`.</span></span>  <span data-ttu-id="fd268-161">Это делается путем вызова метода `Invoke` делегата с помощью оператора `?.` для доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="fd268-161">You'll call the delegate's `Invoke` method using the `?.` operator to access the member.</span></span> <span data-ttu-id="fd268-162">Вы увидите пример в статье [Шаблоны делегатов](../delegates-patterns.md#handling-null-delegates).</span><span class="sxs-lookup"><span data-stu-id="fd268-162">You can see an example in the [delegate patterns](../delegates-patterns.md#handling-null-delegates) article.</span></span>

<span data-ttu-id="fd268-163">Правила оператора `?.` гарантируют, что левая часть оператора вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="fd268-163">The rules of the `?.` operator ensure that the left-hand side of the operator is evaluated only once.</span></span> <span data-ttu-id="fd268-164">Это обеспечивает поддержку многих идиом, включая пример с использованием обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="fd268-164">It enables many idioms, including the following example using event handlers:</span></span>

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

<span data-ttu-id="fd268-165">Обеспечение того, что левая часть вычисляется только один раз, также позволяет использовать любое выражение, включая вызовы методов, в левой части `?.`</span><span class="sxs-lookup"><span data-stu-id="fd268-165">Ensuring that the left side is evaluated only once also enables you to use any expression, including method calls, on the left side of the `?.`</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="fd268-166">Интерполяция строк</span><span class="sxs-lookup"><span data-stu-id="fd268-166">String interpolation</span></span>

<span data-ttu-id="fd268-167">В C# 6 новая функция [интерполяции строк](../language-reference/tokens/interpolated.md) позволяет внедрять выражения в строку.</span><span class="sxs-lookup"><span data-stu-id="fd268-167">With C# 6, the new [string interpolation](../language-reference/tokens/interpolated.md) feature enables you to embed expressions in a string.</span></span> <span data-ttu-id="fd268-168">Просто добавьте перед строкой префикс `$` и используйте выражения между `{` и `}` вместо порядковых номеров:</span><span class="sxs-lookup"><span data-stu-id="fd268-168">Simply preface the string with `$`and use expressions between `{` and `}` instead of ordinals:</span></span>

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

<span data-ttu-id="fd268-169">В этом примере для замененных выражений используются свойства.</span><span class="sxs-lookup"><span data-stu-id="fd268-169">This example uses properties for the substituted expressions.</span></span> <span data-ttu-id="fd268-170">Можно использовать любое выражение.</span><span class="sxs-lookup"><span data-stu-id="fd268-170">You can use any expression.</span></span> <span data-ttu-id="fd268-171">Например, можно вычислить средний балл учащегося как часть интерполяции:</span><span class="sxs-lookup"><span data-stu-id="fd268-171">For example, you could compute a student's grade point average as part of the interpolation:</span></span>

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

<span data-ttu-id="fd268-172">Предыдущая строка кода форматирует значение для `Grades.Average()` как число с плавающей запятой с двумя десятичными разрядами.</span><span class="sxs-lookup"><span data-stu-id="fd268-172">The preceding line of code formats the value for `Grades.Average()` as a floating-point number with two decimal places.</span></span>

<span data-ttu-id="fd268-173">Часто требуется отформатировать строку, полученную с использованием конкретного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="fd268-173">Often, you may need to format the string produced using a specific culture.</span></span> <span data-ttu-id="fd268-174">Для этого положитесь на тот факт, что объект, созданный в результате интерполяции строк, можно неявно преобразовывать в <xref:System.FormattableString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd268-174">You use the fact that the object produced by a string interpolation can be implicitly converted to <xref:System.FormattableString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fd268-175">Экземпляр <xref:System.FormattableString> содержит составную строку формата и результаты вычисления выражений до преобразования в строки.</span><span class="sxs-lookup"><span data-stu-id="fd268-175">The <xref:System.FormattableString> instance contains the composite format string and the results of evaluating the expressions before converting them to strings.</span></span> <span data-ttu-id="fd268-176">С помощью метода <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> вы можете явно указать язык и региональные параметры при форматировании строки.</span><span class="sxs-lookup"><span data-stu-id="fd268-176">Use the <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> method to specify the culture when formatting a string.</span></span> <span data-ttu-id="fd268-177">Так, приведенный ниже пример создает строку, используя немецкий язык (de-DE) в качестве языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="fd268-177">The following example produces a string using the German (de-DE) culture.</span></span> <span data-ttu-id="fd268-178">(В качестве десятичного разделителя в немецком обычно используется символ ",", а "." — в качестве разделителя тысяч.)</span><span class="sxs-lookup"><span data-stu-id="fd268-178">(By default, the German culture uses the ',' character for the decimal separator, and the '.' character as the thousands separator.)</span></span>

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

<span data-ttu-id="fd268-179">Чтобы начать работу с интерполяцией строк, см. интерактивный учебник [Интерполяция строк в C#](../tutorials/exploration/interpolated-strings.yml), статью [Интерполяция](../language-reference/tokens/interpolated.md) и учебник [Интерполяция строк в C#](../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="fd268-179">To get started with string interpolation, see the [String interpolation in C#](../tutorials/exploration/interpolated-strings.yml) interactive tutorial, the [String interpolation](../language-reference/tokens/interpolated.md) article, and the [String interpolation in C#](../tutorials/string-interpolation.md) tutorial.</span></span>

## <a name="exception-filters"></a><span data-ttu-id="fd268-180">Фильтры исключений</span><span class="sxs-lookup"><span data-stu-id="fd268-180">Exception filters</span></span>

<span data-ttu-id="fd268-181">*Фильтры исключений* — это предложения, которые определяют, когда должно применяться данное предложение catch.</span><span class="sxs-lookup"><span data-stu-id="fd268-181">*Exception Filters* are clauses that determine when a given catch clause should be applied.</span></span> <span data-ttu-id="fd268-182">Если выражение, используемое для фильтра исключений, принимает значение `true`, предложение catch выполняет обычную обработку исключения.</span><span class="sxs-lookup"><span data-stu-id="fd268-182">If the expression used for an exception filter evaluates to `true`, the catch clause performs its normal processing on an exception.</span></span> <span data-ttu-id="fd268-183">Если выражение принимает значение `false`, то предложение `catch` пропускается.</span><span class="sxs-lookup"><span data-stu-id="fd268-183">If the expression evaluates to `false`, then the `catch` clause is skipped.</span></span> <span data-ttu-id="fd268-184">Например, эту функцию можно использовать для просмотра сведений об исключении, чтобы определить, может ли предложение `catch` обработать исключение:</span><span class="sxs-lookup"><span data-stu-id="fd268-184">One use is to examine information about an exception to determine if a `catch` clause can process the exception:</span></span>

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

## <a name="the-nameof-expression"></a><span data-ttu-id="fd268-185">Выражение `nameof`</span><span class="sxs-lookup"><span data-stu-id="fd268-185">The `nameof` expression</span></span>

<span data-ttu-id="fd268-186">Результатом применения выражения [nameof](../language-reference/operators/nameof.md) является имя символа.</span><span class="sxs-lookup"><span data-stu-id="fd268-186">The [nameof](../language-reference/operators/nameof.md) expression evaluates to the name of a symbol.</span></span> <span data-ttu-id="fd268-187">Это отличный способ заставить инструменты работать, если вам требуется имя переменной, свойства или поля члена.</span><span class="sxs-lookup"><span data-stu-id="fd268-187">It's a great way to get tools working whenever you need the name of a variable, a property, or a member field.</span></span> <span data-ttu-id="fd268-188">Одно из наиболее распространенных применений `nameof` — предоставление имени символа, который вызвал исключение:</span><span class="sxs-lookup"><span data-stu-id="fd268-188">One of the most common uses for `nameof` is to provide the name of a symbol that caused an exception:</span></span>

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

<span data-ttu-id="fd268-189">Другая сфера применения — с приложениями на основе XAML, реализующими интерфейс `INotifyPropertyChanged`:</span><span class="sxs-lookup"><span data-stu-id="fd268-189">Another use is with XAML-based applications that implement the `INotifyPropertyChanged` interface:</span></span>

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

## <a name="await-in-catch-and-finally-blocks"></a><span data-ttu-id="fd268-190">Выражение Await в блоках Catch и Finally</span><span class="sxs-lookup"><span data-stu-id="fd268-190">Await in Catch and Finally blocks</span></span>

<span data-ttu-id="fd268-191">В C# 5 было несколько ограничений в отношении размещения выражений `await`.</span><span class="sxs-lookup"><span data-stu-id="fd268-191">C# 5 had several limitations around where you could place `await` expressions.</span></span> <span data-ttu-id="fd268-192">В C# 6 вы можете использовать `await` в выражениях `catch` или `finally`.</span><span class="sxs-lookup"><span data-stu-id="fd268-192">With C# 6, you can now use `await` in `catch` or `finally` expressions.</span></span> <span data-ttu-id="fd268-193">Чаще всего это используется в сценариях ведения журнала:</span><span class="sxs-lookup"><span data-stu-id="fd268-193">This is most often used with logging scenarios:</span></span>

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

<span data-ttu-id="fd268-194">Реализация добавления поддержки `await` внутри предложений `catch` и `finally` гарантирует согласованность поведения с поведением для синхронного кода.</span><span class="sxs-lookup"><span data-stu-id="fd268-194">The implementation details for adding `await` support inside `catch` and `finally` clauses ensure that the behavior is consistent with the behavior for synchronous code.</span></span> <span data-ttu-id="fd268-195">Если код, выполняемый в предложении `catch` или `finally`, создает исключение, выполнение ищет подходящее предложение `catch` в следующем окружающем блоке.</span><span class="sxs-lookup"><span data-stu-id="fd268-195">When code executed in a `catch` or `finally` clause throws, execution looks for a suitable `catch` clause in the next surrounding block.</span></span> <span data-ttu-id="fd268-196">При наличии текущего исключения это исключение будет потеряно.</span><span class="sxs-lookup"><span data-stu-id="fd268-196">If there was a current exception, that exception is lost.</span></span> <span data-ttu-id="fd268-197">То же самое происходит с ожидаемыми выражениями в предложениях `catch` и `finally`: выполняется поиск подходящего `catch`, а текущее исключение (при наличии) утрачивается.</span><span class="sxs-lookup"><span data-stu-id="fd268-197">The same happens with awaited expressions in `catch` and `finally` clauses: a suitable `catch` is searched for, and the current exception, if any, is lost.</span></span>  

> [!NOTE]
> <span data-ttu-id="fd268-198">Это поведение лежит в основе рекомендации тщательного написания предложений `catch` и `finally` во избежание внесения новых исключений.</span><span class="sxs-lookup"><span data-stu-id="fd268-198">This behavior is the reason it's recommended to write `catch` and `finally` clauses carefully, to avoid introducing new exceptions.</span></span>

## <a name="initialize-associative-collections-using-indexers"></a><span data-ttu-id="fd268-199">Инициализация ассоциативных коллекций с помощью индексаторов</span><span class="sxs-lookup"><span data-stu-id="fd268-199">Initialize associative collections using indexers</span></span>

<span data-ttu-id="fd268-200">*Инициализаторы индекса* — это одна из двух функций, обеспечивающих согласованность инициализаторов коллекций с использованием индексов.</span><span class="sxs-lookup"><span data-stu-id="fd268-200">*Index Initializers* is one of two features that make collection initializers more consistent with index usage.</span></span> <span data-ttu-id="fd268-201">В более ранних версиях C# можно было использовать *инициализаторы коллекций* с коллекциями типа последовательности, включая <xref:System.Collections.Generic.Dictionary%602>, заключая пару ключ-значение в фигурные скобки:</span><span class="sxs-lookup"><span data-stu-id="fd268-201">In earlier releases of C#, you could use *collection initializers* with sequence style collections, including <xref:System.Collections.Generic.Dictionary%602>, by adding braces around key and value pairs:</span></span>

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#CollectionInitializer)]

<span data-ttu-id="fd268-202">Вы можете использовать их с коллекциями <xref:System.Collections.Generic.Dictionary%602> и другими типами, где доступный метод `Add` принимает более одного аргумента.</span><span class="sxs-lookup"><span data-stu-id="fd268-202">You can use them with <xref:System.Collections.Generic.Dictionary%602> collections and other types where the accessible `Add` method accepts more than one argument.</span></span> <span data-ttu-id="fd268-203">Новый синтаксис поддерживает назначение в коллекцию с помощью индекса:</span><span class="sxs-lookup"><span data-stu-id="fd268-203">The new syntax supports assignment using an index into the collection:</span></span>

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

<span data-ttu-id="fd268-204">Эта функция означает, что ассоциативные контейнеры могут быть инициализированы с помощью синтаксиса, аналогичного используемому для контейнеров последовательностей для нескольких версий.</span><span class="sxs-lookup"><span data-stu-id="fd268-204">This feature means that associative containers can be initialized using syntax similar to what's been in place for sequence containers for several versions.</span></span>

## <a name="extension-add-methods-in-collection-initializers"></a><span data-ttu-id="fd268-205">Методы расширения `Add` в инициализаторах коллекций</span><span class="sxs-lookup"><span data-stu-id="fd268-205">Extension `Add` methods in collection initializers</span></span>

<span data-ttu-id="fd268-206">Еще одна функция, упрощающая инициализацию коллекций, — это возможность использования *метода расширения* для метода `Add`.</span><span class="sxs-lookup"><span data-stu-id="fd268-206">Another feature that makes collection initialization easier is the ability to use an *extension method* for the `Add` method.</span></span> <span data-ttu-id="fd268-207">Эта функция была добавлена для согласования с Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fd268-207">This feature was added for parity with Visual Basic.</span></span> <span data-ttu-id="fd268-208">Она наиболее удобна при наличии пользовательского класса коллекции, имеющего метод с другим именем для семантического добавления новых элементов.</span><span class="sxs-lookup"><span data-stu-id="fd268-208">The feature is most useful when you have a custom collection class that has a method with a different name to semantically add new items.</span></span>

## <a name="improved-overload-resolution"></a><span data-ttu-id="fd268-209">Улучшенное разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="fd268-209">Improved overload resolution</span></span>

<span data-ttu-id="fd268-210">Эта последняя функция, на которую вы, вероятно, не обратите внимания.</span><span class="sxs-lookup"><span data-stu-id="fd268-210">This last feature is one you probably won't notice.</span></span> <span data-ttu-id="fd268-211">Есть примеры того, что предыдущая версия компилятора C# могла определять некоторые вызовы методов, работающих с лямбда-выражениями, как неоднозначные.</span><span class="sxs-lookup"><span data-stu-id="fd268-211">There were constructs where the previous version of the C# compiler may have found some method calls involving lambda expressions ambiguous.</span></span> <span data-ttu-id="fd268-212">Рассмотрим этот метод:</span><span class="sxs-lookup"><span data-stu-id="fd268-212">Consider this method:</span></span>

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

<span data-ttu-id="fd268-213">В более ранних версиях C# вызов этого метода с использованием синтаксиса группы методов приведет к сбою:</span><span class="sxs-lookup"><span data-stu-id="fd268-213">In earlier versions of C#, calling that method using the method group syntax would fail:</span></span>

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]

<span data-ttu-id="fd268-214">Компилятор прежних версий не мог правильно различать методы `Task.Run(Action)` и `Task.Run(Func<Task>())`.</span><span class="sxs-lookup"><span data-stu-id="fd268-214">The earlier compiler couldn't distinguish correctly between `Task.Run(Action)` and `Task.Run(Func<Task>())`.</span></span> <span data-ttu-id="fd268-215">В предыдущих версиях вам бы потребовалось использовать лямбда-выражение в качестве аргумента:</span><span class="sxs-lookup"><span data-stu-id="fd268-215">In previous versions, you'd need to use a lambda expression as an argument:</span></span>

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

<span data-ttu-id="fd268-216">Компилятор C# 6 правильно определяет, что `Task.Run(Func<Task>())` является лучшим вариантом.</span><span class="sxs-lookup"><span data-stu-id="fd268-216">The C# 6 compiler correctly determines that `Task.Run(Func<Task>())` is a better choice.</span></span>

### <a name="deterministic-compiler-output"></a><span data-ttu-id="fd268-217">Детерминированные выходные данные компилятора</span><span class="sxs-lookup"><span data-stu-id="fd268-217">Deterministic compiler output</span></span>

<span data-ttu-id="fd268-218">Параметр `-deterministic` дает компилятору инструкцию создать полностью идентичную выходную сборку для последовательных компиляций одного исходного файла.</span><span class="sxs-lookup"><span data-stu-id="fd268-218">The `-deterministic` option instructs the compiler to produce a byte-for-byte identical output assembly for successive compilations of the same source files.</span></span>

<span data-ttu-id="fd268-219">По умолчанию каждая компиляция выдает уникальные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="fd268-219">By default, every compilation produces unique output on each compilation.</span></span> <span data-ttu-id="fd268-220">Компилятор добавляет метку времени и идентификатор GUID из случайных чисел.</span><span class="sxs-lookup"><span data-stu-id="fd268-220">The compiler adds a timestamp, and a GUID generated from random numbers.</span></span> <span data-ttu-id="fd268-221">Используйте этот параметр для побайтового сравнения выходных данных и гарантии согласованности сборок.</span><span class="sxs-lookup"><span data-stu-id="fd268-221">You use this option if you want to compare the byte-for-byte output to ensure consistency across builds.</span></span>

<span data-ttu-id="fd268-222">Дополнительные сведения см. в статье [Параметр компилятора -deterministic](../language-reference/compiler-options/deterministic-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="fd268-222">For more information, see the [-deterministic compiler option](../language-reference/compiler-options/deterministic-compiler-option.md) article.</span></span>
