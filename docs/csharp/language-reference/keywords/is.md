---
title: is (Справочник по C#)
keywords: ключевое слово is(C#), is (C#)
ms.date: 02/17/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44c15eb9d65adf10904f8777847b0653ff1dbc99
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="is-c-reference"></a><span data-ttu-id="bc14c-103">is (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bc14c-103">is (C# Reference)</span></span> #

<span data-ttu-id="bc14c-104">Проверяет совместимость объекта с заданным типом или (начиная с C# 7.0) проверяет выражение на соответствие шаблону.</span><span class="sxs-lookup"><span data-stu-id="bc14c-104">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="bc14c-105">Тестирование на совместимость типов</span><span class="sxs-lookup"><span data-stu-id="bc14c-105">Testing for type compatibility</span></span> ##

<span data-ttu-id="bc14c-106">Ключевое слово `is` оценивает совместимость типов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc14c-106">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="bc14c-107">Оно определяет, может ли экземпляр объекта или результат выражения быть преобразован в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="bc14c-107">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="bc14c-108">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bc14c-108">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="bc14c-109">где *expr* — это выражение, значением которого является экземпляр какого-либо типа, а *type* — это имя типа, в который должен быть преобразован результат *expr*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-109">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="bc14c-110">Оператор `is` принимает значение `true`, если выражение *expr* отлично от NULL и объект, являющийся результатом вычисления выражения, может быть преобразован в тип *type*. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="bc14c-110">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="bc14c-111">Например, следующий код определяет, может ли `obj` быть приведен к экземпляру типа `Person`:</span><span class="sxs-lookup"><span data-stu-id="bc14c-111">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="bc14c-112">Оператор `is` принимает значение true, если:</span><span class="sxs-lookup"><span data-stu-id="bc14c-112">The `is` statement is true if:</span></span>

- <span data-ttu-id="bc14c-113">*expr* представляет собой экземпляр того же типа, что и *type*;</span><span class="sxs-lookup"><span data-stu-id="bc14c-113">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="bc14c-114">*expr* является экземпляром типа, производного от *type*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-114">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="bc14c-115">Другими словами, результат *expr* может быть приведен с повышением к экземпляру *type*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-115">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="bc14c-116">*expr* имеет тип времени компиляции, который является базовым классом для *type*, и *expr* имеет тип среды выполнения, который является *type* или производным от *type*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-116">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="bc14c-117">*Тип времени компиляции* переменной представляет собой тип переменной, как определено в объявлении.</span><span class="sxs-lookup"><span data-stu-id="bc14c-117">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="bc14c-118">*Тип среды выполнения* переменной представляет собой тип экземпляра, назначенный этой переменной.</span><span class="sxs-lookup"><span data-stu-id="bc14c-118">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="bc14c-119">*expr* является экземпляром типа, который реализует интерфейс *type*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-119">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="bc14c-120">В следующем примере показано, что выражение `is` принимает значение `true` для каждого из этих преобразований.</span><span class="sxs-lookup"><span data-stu-id="bc14c-120">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="bc14c-121">Ключевое слово `is` создает предупреждение во время компиляции, если известно, что выражение всегда будет иметь значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="bc14c-121">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="bc14c-122">Оно рассматривает только преобразование ссылок, упаковки-преобразования и распаковки-преобразования. Определенные пользователем преобразования или преобразования, определенные с помощью операторов [implicit](implicit.md) и [explicit](explicit.md) типа не учитываются.</span><span class="sxs-lookup"><span data-stu-id="bc14c-122">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="bc14c-123">Следующий пример создает предупреждения, так как результат преобразования известен во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="bc14c-123">The following example generates warnings because the result of the conversion is known at compile-time.</span></span> <span data-ttu-id="bc14c-124">Обратите внимание, что выражение `is` для преобразований из `int` в `long` и `double` возвращает значение false, так как эти преобразования обрабатываются оператором [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="bc14c-124">Note that the `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="bc14c-125">`expr` может быть любым выражением, возвращающим значение, за исключением анонимных методов и лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="bc14c-125">`expr` can be any expression that returns a value, with the exception of anonymous methods and lambda expressions.</span></span> <span data-ttu-id="bc14c-126">В следующем примере используется `is` для определения возвращаемого значения вызова метода.</span><span class="sxs-lookup"><span data-stu-id="bc14c-126">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="bc14c-127">Начиная с C# 7.0 можно использовать сопоставление шаблонов с [шаблоном типа](#type), чтобы создавать лаконичный код, использующий оператор `is`.</span><span class="sxs-lookup"><span data-stu-id="bc14c-127">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="bc14c-128">Сопоставление шаблонов с `is`</span><span class="sxs-lookup"><span data-stu-id="bc14c-128">Pattern matching with `is`</span></span> ##

<span data-ttu-id="bc14c-129">Начиная с C# 7.0 операторы `is` и [switch](../../../csharp/language-reference/keywords/switch.md) поддерживают сопоставление шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bc14c-129">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="bc14c-130">Ключевое слово `is` поддерживает следующие шаблоны:</span><span class="sxs-lookup"><span data-stu-id="bc14c-130">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="bc14c-131">[Шаблон типа](#type), который проверяет, можно ли преобразовать выражение в указанный тип и, если можно, приводит его к переменной этого типа.</span><span class="sxs-lookup"><span data-stu-id="bc14c-131">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="bc14c-132">[Шаблон константы](#constant), который проверяет, получает ли выражение указанное постоянное значение.</span><span class="sxs-lookup"><span data-stu-id="bc14c-132">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="bc14c-133">[Шаблон переменной](#var) — совпадение всегда является успешным и привязывает значение выражения к новой локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="bc14c-133">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <span data-ttu-id="bc14c-134"><a name="type" /> Шаблон типа </a></span><span class="sxs-lookup"><span data-stu-id="bc14c-134"><a name="type" /> Type pattern </a></span></span>

<span data-ttu-id="bc14c-135">При использовании шаблона типа для сопоставления шаблонов `is` проверяет, можно ли преобразовать выражение в указанный тип и, если это возможно, приводит его к переменной этого типа.</span><span class="sxs-lookup"><span data-stu-id="bc14c-135">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="bc14c-136">Это просто расширение оператора `is`, для краткого определения и преобразования типа.</span><span class="sxs-lookup"><span data-stu-id="bc14c-136">It is a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="bc14c-137">Шаблон типа `is` имеет следующий общий вид:</span><span class="sxs-lookup"><span data-stu-id="bc14c-137">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="bc14c-138">где *expr* — это выражение, значением которого является экземпляр какого-либо типа, *type* — это имя типа, в который должен быть преобразован результат *expr*, *varname* — это объект, в который преобразуется результат *expr*, если проверка `is` возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="bc14c-138">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="bc14c-139">Выражение `is` имеет значение `true`, если выполняется одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="bc14c-139">The `is` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="bc14c-140">*expr* представляет собой экземпляр того же типа, что и *type*;</span><span class="sxs-lookup"><span data-stu-id="bc14c-140">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="bc14c-141">*expr* является экземпляром типа, производного от *type*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-141">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="bc14c-142">Другими словами, результат *expr* может быть приведен с повышением к экземпляру *type*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-142">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="bc14c-143">*expr* имеет тип времени компиляции, который является базовым классом для *type*, и *expr* имеет тип среды выполнения, который является *type* или производным от *type*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-143">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="bc14c-144">*Тип времени компиляции* переменной представляет собой тип переменной, как определено в объявлении.</span><span class="sxs-lookup"><span data-stu-id="bc14c-144">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="bc14c-145">*Тип среды выполнения* переменной представляет собой тип экземпляра, назначенный этой переменной.</span><span class="sxs-lookup"><span data-stu-id="bc14c-145">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="bc14c-146">*expr* является экземпляром типа, который реализует интерфейс *type*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-146">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="bc14c-147">Если *exp* имеет значение `true` и `is` используется с оператором `if`, назначается *varname* и получает локальную область видимости в пределах только оператора `if`.</span><span class="sxs-lookup"><span data-stu-id="bc14c-147">If *exp* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="bc14c-148">В следующем примере используется шаблон типа `is`, который обеспечивает реализацию метода <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> типа.</span><span class="sxs-lookup"><span data-stu-id="bc14c-148">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="bc14c-149">Без сопоставления шаблонов этот код может быть написан следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bc14c-149">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="bc14c-150">При использовании шаблона типа создается более лаконичный и удобочитаемый код, причем проверять результат преобразования (`null`) не требуется.</span><span class="sxs-lookup"><span data-stu-id="bc14c-150">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="bc14c-151">Шаблон типа `is` также позволяет создавать более компактный код при определении типа для типа значения.</span><span class="sxs-lookup"><span data-stu-id="bc14c-151">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="bc14c-152">В следующем примере используется шаблон типа `is`, чтобы определить, является ли объект экземпляром `Person` или `Dog` перед отображением значения соответствующего свойства.</span><span class="sxs-lookup"><span data-stu-id="bc14c-152">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="bc14c-153">Для эквивалентного кода без сопоставления шаблонов требуется отдельное назначение, которое включает явное приведение.</span><span class="sxs-lookup"><span data-stu-id="bc14c-153">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="bc14c-154"><a name="constant" /> Шаблон константы</span><span class="sxs-lookup"><span data-stu-id="bc14c-154"><a name="constant" /> Constant pattern</span></span> ###

<span data-ttu-id="bc14c-155">При выполнении сопоставления с шаблоном константы `is` проверяет, равно ли выражение указанной константе.</span><span class="sxs-lookup"><span data-stu-id="bc14c-155">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="bc14c-156">В C# 6 и более ранних версиях шаблон константы поддерживается оператором [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="bc14c-156">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="bc14c-157">Начиная с C# 7.0 он поддерживается и оператором `is`.</span><span class="sxs-lookup"><span data-stu-id="bc14c-157">Starting with C# 7.0, it is supported by the `is` statement as well.</span></span> <span data-ttu-id="bc14c-158">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bc14c-158">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="bc14c-159">где *expr* — это выражение для вычисления, а *constant* — это значение, которое нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="bc14c-159">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="bc14c-160">*constant* может быть любой из следующих константных выражений:</span><span class="sxs-lookup"><span data-stu-id="bc14c-160">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="bc14c-161">литеральное значение;</span><span class="sxs-lookup"><span data-stu-id="bc14c-161">A literal value.</span></span>

- <span data-ttu-id="bc14c-162">имя объявленной переменной `const`;</span><span class="sxs-lookup"><span data-stu-id="bc14c-162">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="bc14c-163">константа перечисления.</span><span class="sxs-lookup"><span data-stu-id="bc14c-163">An enumeration constant.</span></span>

<span data-ttu-id="bc14c-164">Константное выражение вычисляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bc14c-164">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="bc14c-165">Если *expr* и *constant* являются целочисленными типами, оператор равенства C# определяет, возвращает ли выражение `true` (то есть выполняется ли условие `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="bc14c-165">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="bc14c-166">В противном случае значение выражения определяется с помощью вызова статического метода [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="bc14c-166">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="bc14c-167">В следующем примере шаблон типа и шаблон константы объединяются для проверки того, является ли объект экземпляром `Dice` и, если это так, определяют, равно ли 6 значение броска кости.</span><span class="sxs-lookup"><span data-stu-id="bc14c-167">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]
 
### <span data-ttu-id="bc14c-168"><a name="var" /> Шаблон переменной </a></span><span class="sxs-lookup"><span data-stu-id="bc14c-168"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="bc14c-169">Сопоставление шаблону переменной всегда завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="bc14c-169">A pattern match with the var pattern always succeeds.</span></span> <span data-ttu-id="bc14c-170">Оно имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="bc14c-170">Its syntax is</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="bc14c-171">где значение *expr* всегда назначается локальной переменной с именем *varname*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-171">where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="bc14c-172">*varname* является статической переменной того же типа, что и *expr*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-172">*varname* is a static variable of the same type as *expr*.</span></span> <span data-ttu-id="bc14c-173">В следующем примере шаблон переменной используется для назначения выражения переменной с именем `obj`.</span><span class="sxs-lookup"><span data-stu-id="bc14c-173">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="bc14c-174">Затем отображается значение и тип `obj`.</span><span class="sxs-lookup"><span data-stu-id="bc14c-174">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="bc14c-175">Обратите внимание, что если *expr* — `null`, `is` выражение, по-прежнему имеет значение true и назначает `null` для *varname*.</span><span class="sxs-lookup"><span data-stu-id="bc14c-175">Note that if *expr* is `null`, the `is` expression still is true and assigns `null` to *varname*.</span></span> 

# <a name="c-language-specification"></a><span data-ttu-id="bc14c-176">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="bc14c-176">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bc14c-177">См. также</span><span class="sxs-lookup"><span data-stu-id="bc14c-177">See also</span></span>  
 [<span data-ttu-id="bc14c-178">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bc14c-178">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="bc14c-179">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="bc14c-179">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="bc14c-180">typeof</span><span class="sxs-lookup"><span data-stu-id="bc14c-180">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)  
 [<span data-ttu-id="bc14c-181">as</span><span class="sxs-lookup"><span data-stu-id="bc14c-181">as</span></span>](../../../csharp/language-reference/keywords/as.md)  
 [<span data-ttu-id="bc14c-182">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="bc14c-182">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
