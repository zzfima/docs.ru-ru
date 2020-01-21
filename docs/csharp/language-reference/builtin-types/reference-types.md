---
title: Встроенные ссылочные типы — справочник по C#
description: Дополнительные сведения о ссылочных типах, имеющих ключевые слова C#, которые можно использовать для их объявления.
ms.date: 06/25/2019
f1_keywords:
- object_CSharpKeyword
- object
- delegate_CSharpKeyword
- delegate
- dynamic_CSharpKeyword
- string
- string_CSharpKeyword
helpviewer_keywords:
- object keyword [C#]
- delegate keyword [C#]
- function pointers [C#]
- dynamic [C#]
- dynamic keyword [C#]
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.openlocfilehash: d5ca0593d802d331d980cf35c701e0a79d54abee
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163102"
---
# <a name="built-in-reference-types-c-reference"></a><span data-ttu-id="0617d-103">Встроенные ссылочные типы (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0617d-103">Built-in reference types (C# reference)</span></span>

<span data-ttu-id="0617d-104">В C# есть ряд встроенных ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="0617d-104">C# has a number of built-in reference types.</span></span> <span data-ttu-id="0617d-105">У них есть ключевые слова или операторы, которые являются синонимами типа в библиотеке .NET.</span><span class="sxs-lookup"><span data-stu-id="0617d-105">They have keywords or operators that are synonyms for a type in the .NET library.</span></span> 

## <a name="the-object-type"></a><span data-ttu-id="0617d-106">Тип object</span><span class="sxs-lookup"><span data-stu-id="0617d-106">The object type</span></span>

<span data-ttu-id="0617d-107">Тип `object` является псевдонимом <xref:System.Object?displayProperty=nameWithType> в .NET.</span><span class="sxs-lookup"><span data-stu-id="0617d-107">The `object` type is an alias for <xref:System.Object?displayProperty=nameWithType> in .NET.</span></span> <span data-ttu-id="0617d-108">В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0617d-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0617d-109">Переменным типа `object` можно назначать значения любого типа.</span><span class="sxs-lookup"><span data-stu-id="0617d-109">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="0617d-110">Любой переменной `object` можно назначить значение по умолчанию с помощью литерала `null`.</span><span class="sxs-lookup"><span data-stu-id="0617d-110">Any `object` variable can be assigned to its default value using the literal `null`.</span></span> <span data-ttu-id="0617d-111">Если переменная типа значения преобразуется в объект, она считается *упакованной*.</span><span class="sxs-lookup"><span data-stu-id="0617d-111">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="0617d-112">Если переменная типа `object` преобразуется в тип значения, она считается *распакованной*.</span><span class="sxs-lookup"><span data-stu-id="0617d-112">When a variable of type `object` is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="0617d-113">Дополнительные сведения см. в разделе [Упаковка-преобразование и распаковка-преобразование](../../programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="0617d-113">For more information, see [Boxing and Unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span></span> 

## <a name="the-string-type"></a><span data-ttu-id="0617d-114">Тип string</span><span class="sxs-lookup"><span data-stu-id="0617d-114">The string type</span></span>

<span data-ttu-id="0617d-115">Тип `string` представляет последовательность, состоящую из нуля или более символов в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="0617d-115">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="0617d-116">`string` является псевдонимом для <xref:System.String?displayProperty=nameWithType> в .NET.</span><span class="sxs-lookup"><span data-stu-id="0617d-116">`string` is an alias for <xref:System.String?displayProperty=nameWithType> in .NET.</span></span>

<span data-ttu-id="0617d-117">Несмотря на то что `string` представляет собой ссылочный тип, [операторы равенства `==` и `!=`](../operators/equality-operators.md#string-equality) по определению сравнивают не ссылки, а значения объектов `string`.</span><span class="sxs-lookup"><span data-stu-id="0617d-117">Although `string` is a reference type, the [equality operators `==` and `!=`](../operators/equality-operators.md#string-equality) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="0617d-118">Это делает проверку равенства строк более интуитивно понятной.</span><span class="sxs-lookup"><span data-stu-id="0617d-118">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="0617d-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="0617d-119">For example:</span></span>

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

<span data-ttu-id="0617d-120">Отображается значение True, а затем False, поскольку содержимое строк эквивалентно, однако `a` и `b` не относятся к одному и тому же экземпляру строки.</span><span class="sxs-lookup"><span data-stu-id="0617d-120">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>

<span data-ttu-id="0617d-121">[Оператор +](../operators/addition-operator.md#string-concatenation) объединяет строки:</span><span class="sxs-lookup"><span data-stu-id="0617d-121">The [+ operator](../operators/addition-operator.md#string-concatenation) concatenates strings:</span></span>

```csharp
string a = "good " + "morning";
```

<span data-ttu-id="0617d-122">При этом создается строковый объект, содержащий слова "good morning".</span><span class="sxs-lookup"><span data-stu-id="0617d-122">This creates a string object that contains "good morning".</span></span>

<span data-ttu-id="0617d-123">Строки *неизменяемы*, т. е. содержимое созданного строкового объекта изменить нельзя, хотя синтаксис выглядит так, будто это возможно.</span><span class="sxs-lookup"><span data-stu-id="0617d-123">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="0617d-124">Например, при написании кода компилятор фактически создает новый строковый объект для хранения новой последовательности символов, а затем этот новый объект назначается `b`.</span><span class="sxs-lookup"><span data-stu-id="0617d-124">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to `b`.</span></span> <span data-ttu-id="0617d-125">Память, выделенная для `b` (если он содержит строку h), затем доступна для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0617d-125">The memory that had been allocated for `b` (when it contained the string "h") is then eligible for garbage collection.</span></span>

```csharp
string b = "h";
b += "ello";
```

<span data-ttu-id="0617d-126">[Оператор](../operators/member-access-operators.md#indexer-operator-) `[]` позволяет предоставить к отдельным символам строки доступ только на чтение.</span><span class="sxs-lookup"><span data-stu-id="0617d-126">The `[]` [operator](../operators/member-access-operators.md#indexer-operator-) can be used for readonly access to individual characters of a string.</span></span> <span data-ttu-id="0617d-127">Допустимые значения индекса начинаются с `0` и должны быть меньше, чем длина строки:</span><span class="sxs-lookup"><span data-stu-id="0617d-127">Valid index values start at `0` and must be less than the length of the string:</span></span>

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

<span data-ttu-id="0617d-128">Также оператор `[]` можно использовать для итерации каждого символа в строке:</span><span class="sxs-lookup"><span data-stu-id="0617d-128">In similar fashion, the `[]` operator can also be used for iterating over each character in a string:</span></span>

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
``` 

<span data-ttu-id="0617d-129">Строковые литералы имеют тип `string` и могут быть записаны в двух формах: в кавычках (") или в кавычках с префиксом `@`.</span><span class="sxs-lookup"><span data-stu-id="0617d-129">String literals are of type `string` and can be written in two forms, quoted and `@`-quoted.</span></span> <span data-ttu-id="0617d-130">Строковые литералы в кавычках заключаются в двойные кавычки ("):</span><span class="sxs-lookup"><span data-stu-id="0617d-130">Quoted string literals are enclosed in double quotation marks ("):</span></span>

```csharp
"good morning"  // a string literal
```

<span data-ttu-id="0617d-131">Строковые литералы могут содержать любые символьные литералы.</span><span class="sxs-lookup"><span data-stu-id="0617d-131">String literals can contain any character literal.</span></span> <span data-ttu-id="0617d-132">Escape-последовательности включены.</span><span class="sxs-lookup"><span data-stu-id="0617d-132">Escape sequences are included.</span></span> <span data-ttu-id="0617d-133">В следующем примере escape-последовательность `\\` используется для получения обратной косой черты, `\u0066` — для получения буквы f, и `\n` — для получения новой строки.</span><span class="sxs-lookup"><span data-stu-id="0617d-133">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
\\ Output:
\\ \f
\\  F
```

> [!NOTE]
> <span data-ttu-id="0617d-134">Escape-код `\udddd` (где `dddd` состоит из четырех цифр) представляет символ Юникода U+`dddd`.</span><span class="sxs-lookup"><span data-stu-id="0617d-134">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="0617d-135">Также распознаются восьмизначные escape-коды Юникода: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="0617d-135">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>

<span data-ttu-id="0617d-136">[Буквальные строковые литералы](../tokens/verbatim.md) начинаются с `@` и также заключаются в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="0617d-136">[Verbatim string literals](../tokens/verbatim.md) start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="0617d-137">Пример:</span><span class="sxs-lookup"><span data-stu-id="0617d-137">For example:</span></span>

```csharp
@"good morning"  // a string literal
```

<span data-ttu-id="0617d-138">Преимущество буквальных строк состоит в том, что escape-последовательности *не* обрабатываются, что позволяет легко написать, например, полное имя файла Windows:</span><span class="sxs-lookup"><span data-stu-id="0617d-138">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified Windows file name:</span></span>

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

<span data-ttu-id="0617d-139">Чтобы добавить в строку с префиксом @-quoted двойные кавычки, продублируйте их:</span><span class="sxs-lookup"><span data-stu-id="0617d-139">To include a double quotation mark in an @-quoted string, double it:</span></span>

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a><span data-ttu-id="0617d-140">Тип delegate</span><span class="sxs-lookup"><span data-stu-id="0617d-140">The delegate type</span></span>

<span data-ttu-id="0617d-141">Объявление типа делегата аналогично сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="0617d-141">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="0617d-142">Оно имеет возвращаемое значение и любое число параметров любого типа:</span><span class="sxs-lookup"><span data-stu-id="0617d-142">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

<span data-ttu-id="0617d-143">В .NET типы `System.Action` и `System.Func` предоставляют общие определения для многих распространенных делегатов.</span><span class="sxs-lookup"><span data-stu-id="0617d-143">In .NET, `System.Action` and `System.Func` types provide generic definitions for many common delegates.</span></span> <span data-ttu-id="0617d-144">Скорее всего, не нужно определять новые пользовательские типы делегата.</span><span class="sxs-lookup"><span data-stu-id="0617d-144">You likely don't need to define new custom delegate types.</span></span> <span data-ttu-id="0617d-145">Вместо этого можно создать экземпляры предоставленных универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="0617d-145">Instead, you can create instantiations of the provided generic types.</span></span>

<span data-ttu-id="0617d-146">Ключевое слово `delegate` имеет ссылочный тип, который можно использовать для инкапсуляции именованного или анонимного метода.</span><span class="sxs-lookup"><span data-stu-id="0617d-146">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="0617d-147">Делегаты аналогичны используемым в языке C++ указателям функций, но являются типобезопасными и безопасными.</span><span class="sxs-lookup"><span data-stu-id="0617d-147">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="0617d-148">Сведения о применении делегатов см. в разделах [Делегаты](../../programming-guide/delegates/index.md) и [Универсальные делегаты](../../programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="0617d-148">For applications of delegates, see [Delegates](../../programming-guide/delegates/index.md) and [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span> <span data-ttu-id="0617d-149">Делегаты являются основой [событий](../../programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="0617d-149">Delegates are the basis for [Events](../../programming-guide/events/index.md).</span></span> <span data-ttu-id="0617d-150">Экземпляры делегата могут создаваться путем его связывания с именованным или анонимным методом.</span><span class="sxs-lookup"><span data-stu-id="0617d-150">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span>

<span data-ttu-id="0617d-151">Делегат должен быть создан при помощи метода или лямбда-выражения, имеющего совместимые возвращаемый тип и входные параметры.</span><span class="sxs-lookup"><span data-stu-id="0617d-151">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="0617d-152">Дополнительные сведения о допустимой степени вариации сигнатур методов см. в разделе [Вариативность в делегатах](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="0617d-152">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="0617d-153">Для использования с анонимными методами делегат и код, который должен быть связан с ним, должны быть объявлены вместе.</span><span class="sxs-lookup"><span data-stu-id="0617d-153">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> 

## <a name="the-dynamic-type"></a><span data-ttu-id="0617d-154">Тип dynamic</span><span class="sxs-lookup"><span data-stu-id="0617d-154">The dynamic type</span></span>

<span data-ttu-id="0617d-155">Тип `dynamic` указывает, что использование переменной и ссылок на ее члены обходит проверку типа во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="0617d-155">The `dynamic` type indicates that use of the variable and references to its members bypass compile-time type checking.</span></span> <span data-ttu-id="0617d-156">Такие операции разрешаются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0617d-156">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="0617d-157">Тип `dynamic` упрощает доступ к API COM, таким как API автоматизации Office, к динамическим API, таким как библиотеки IronPython, и к HTML-модели DOM.</span><span class="sxs-lookup"><span data-stu-id="0617d-157">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>

<span data-ttu-id="0617d-158">Тип `dynamic` в большинстве случаев ведет себя как тип `object`.</span><span class="sxs-lookup"><span data-stu-id="0617d-158">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="0617d-159">В частности, можно преобразовать любое выражение, отличное от NULL, в тип `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="0617d-159">In particular, any non-null expression can be converted to the `dynamic` type.</span></span> <span data-ttu-id="0617d-160">Тип `dynamic` отличается от `object` тем, что операции, которые содержат выражения типа `dynamic`, не разрешаются или тип проверяется компилятором.</span><span class="sxs-lookup"><span data-stu-id="0617d-160">The `dynamic` type differs from `object` in that operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="0617d-161">Компилятор объединяет сведения об операции, которые впоследствии будут использоваться для оценки этой операции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0617d-161">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="0617d-162">В рамках этого процесса переменные типа `dynamic` компилируются в переменные типа `object`.</span><span class="sxs-lookup"><span data-stu-id="0617d-162">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="0617d-163">Таким образом, тип `dynamic` существует только во время компиляции, но не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0617d-163">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>

<span data-ttu-id="0617d-164">В следующем примере переменной типа `dynamic` противопоставляется переменная типа `object`.</span><span class="sxs-lookup"><span data-stu-id="0617d-164">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="0617d-165">Чтобы проверить тип каждой переменной во время компиляции, наведите указатель мыши на `dyn` или `obj` в операторах `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="0617d-165">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="0617d-166">Скопируйте следующий код в редактор, где доступен IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0617d-166">Copy the following code into an editor where IntelliSense is available.</span></span> <span data-ttu-id="0617d-167">IntelliSense отображает **dynamic** для `dyn` и **object** для `obj`.</span><span class="sxs-lookup"><span data-stu-id="0617d-167">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

<span data-ttu-id="0617d-168">Операторы <xref:System.Console.WriteLine%2A> отображают типы времени выполнения `dyn` и `obj`.</span><span class="sxs-lookup"><span data-stu-id="0617d-168">The <xref:System.Console.WriteLine%2A> statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="0617d-169">На этом этапе оба имеют один и тот же тип — целое число.</span><span class="sxs-lookup"><span data-stu-id="0617d-169">At that point, both have the same type, integer.</span></span> <span data-ttu-id="0617d-170">Выводятся следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="0617d-170">The following output is produced:</span></span>

```console
System.Int32
System.Int32
```

<span data-ttu-id="0617d-171">Чтобы увидеть разницу между `dyn` и `obj` во время компиляции, добавьте между объявлениями и операторами `WriteLine` в предыдущем примере следующие две строки:</span><span class="sxs-lookup"><span data-stu-id="0617d-171">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 <span data-ttu-id="0617d-172">При попытке добавления целого числа и объекта в выражение `obj + 3` выдается ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="0617d-172">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="0617d-173">При этом для `dyn + 3` ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="0617d-173">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="0617d-174">Выражение, которое содержит `dyn`, не проверяется во время компиляции, поскольку тип `dyn` имеет значение `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="0617d-174">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>

<span data-ttu-id="0617d-175">В следующем примере `dynamic` используется в нескольких объявлениях.</span><span class="sxs-lookup"><span data-stu-id="0617d-175">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="0617d-176">Метод `Main` также противопоставляет проверку типов во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="0617d-176">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a><span data-ttu-id="0617d-177">См. также</span><span class="sxs-lookup"><span data-stu-id="0617d-177">See also</span></span>

- [<span data-ttu-id="0617d-178">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0617d-178">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0617d-179">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="0617d-179">C# Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="0617d-180">События</span><span class="sxs-lookup"><span data-stu-id="0617d-180">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="0617d-181">Использование типа dynamic</span><span class="sxs-lookup"><span data-stu-id="0617d-181">Using Type dynamic</span></span>](../../programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="0617d-182">Рекомендации по использованию строк</span><span class="sxs-lookup"><span data-stu-id="0617d-182">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)
- [<span data-ttu-id="0617d-183">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0617d-183">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="0617d-184">Создание строк</span><span class="sxs-lookup"><span data-stu-id="0617d-184">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="0617d-185">Операторы приведения и тестирования типов</span><span class="sxs-lookup"><span data-stu-id="0617d-185">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
- [<span data-ttu-id="0617d-186">Практическое руководство. Безопасное приведение с помощью сопоставления шаблонов, а также операторов is и as</span><span class="sxs-lookup"><span data-stu-id="0617d-186">How to safely cast using pattern matching and the as and is operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="0617d-187">Пошаговое руководство. Создание и использование динамических объектов (C# и Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0617d-187">Walkthrough: creating and using dynamic objects</span></span>](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
