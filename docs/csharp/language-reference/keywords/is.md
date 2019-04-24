---
title: is. Справочник по C#
ms.custom: seodec18
ms.date: 04/09/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 9fb57caeafde9db5759300d938a85f4abf4d05f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672463"
---
# <a name="is-c-reference"></a><span data-ttu-id="feadc-102">is (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="feadc-102">is (C# Reference)</span></span>

<span data-ttu-id="feadc-103">Проверяет совместимость объекта с заданным типом или (начиная с C# 7.0) проверяет выражение на соответствие шаблону.</span><span class="sxs-lookup"><span data-stu-id="feadc-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="feadc-104">Тестирование на совместимость типов</span><span class="sxs-lookup"><span data-stu-id="feadc-104">Testing for type compatibility</span></span>

<span data-ttu-id="feadc-105">Ключевое слово `is` оценивает совместимость типов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="feadc-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="feadc-106">Оно определяет, может ли экземпляр объекта или результат выражения быть преобразован в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="feadc-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="feadc-107">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="feadc-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="feadc-108">где *expr* — это выражение, значением которого является экземпляр какого-либо типа, а *type* — это имя типа, в который должен быть преобразован результат *expr*.</span><span class="sxs-lookup"><span data-stu-id="feadc-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="feadc-109">Оператор `is` принимает значение `true`, если выражение *expr* отлично от NULL и объект, являющийся результатом вычисления выражения, может быть преобразован в тип *type*. В противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="feadc-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="feadc-110">Например, следующий код определяет, может ли `obj` быть приведен к экземпляру типа `Person`:</span><span class="sxs-lookup"><span data-stu-id="feadc-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="feadc-111">Оператор `is` принимает значение true, если:</span><span class="sxs-lookup"><span data-stu-id="feadc-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="feadc-112">*expr* представляет собой экземпляр того же типа, что и *type*;</span><span class="sxs-lookup"><span data-stu-id="feadc-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="feadc-113">*expr* является экземпляром типа, производного от *type*.</span><span class="sxs-lookup"><span data-stu-id="feadc-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="feadc-114">Другими словами, результат *expr* может быть приведен с повышением к экземпляру *type*.</span><span class="sxs-lookup"><span data-stu-id="feadc-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="feadc-115">*expr* имеет тип времени компиляции, который является базовым классом для *type*, и *expr* имеет тип среды выполнения, который является *type* или производным от *type*.</span><span class="sxs-lookup"><span data-stu-id="feadc-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="feadc-116">*Тип времени компиляции* переменной представляет собой тип переменной, как определено в объявлении.</span><span class="sxs-lookup"><span data-stu-id="feadc-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="feadc-117">*Тип среды выполнения* переменной представляет собой тип экземпляра, назначенный этой переменной.</span><span class="sxs-lookup"><span data-stu-id="feadc-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="feadc-118">*expr* является экземпляром типа, который реализует интерфейс *type*.</span><span class="sxs-lookup"><span data-stu-id="feadc-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="feadc-119">В следующем примере показано, что выражение `is` принимает значение `true` для каждого из этих преобразований.</span><span class="sxs-lookup"><span data-stu-id="feadc-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="feadc-120">Ключевое слово `is` создает предупреждение во время компиляции, если известно, что выражение всегда будет иметь значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="feadc-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="feadc-121">Оно рассматривает только преобразование ссылок, упаковки-преобразования и распаковки-преобразования. Определенные пользователем преобразования или преобразования, определенные с помощью операторов [implicit](implicit.md) и [explicit](explicit.md) типа не учитываются.</span><span class="sxs-lookup"><span data-stu-id="feadc-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="feadc-122">Следующий пример создает предупреждения, так как результат преобразования известен во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="feadc-122">The following example generates warnings because the result of the conversion is known at compile time.</span></span> <span data-ttu-id="feadc-123">Выражение `is` для преобразований из `int` в `long` и `double` возвращает значение false, так как эти преобразования обрабатываются оператором [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="feadc-123">The `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="feadc-124">`expr` не может быть анонимным методом или лямбда-выражением,</span><span class="sxs-lookup"><span data-stu-id="feadc-124">`expr` cannot be an anonymous method or lambda expression.</span></span> <span data-ttu-id="feadc-125">а может быть любым другим выражением, возвращающим значение.</span><span class="sxs-lookup"><span data-stu-id="feadc-125">It can be any other expression that returns a value.</span></span> <span data-ttu-id="feadc-126">В следующем примере используется `is` для определения возвращаемого значения вызова метода.</span><span class="sxs-lookup"><span data-stu-id="feadc-126">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="feadc-127">Начиная с C# 7.0 можно использовать сопоставление шаблонов с [шаблоном типа](#type), чтобы создавать лаконичный код, использующий оператор `is`.</span><span class="sxs-lookup"><span data-stu-id="feadc-127">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="feadc-128">Сопоставление шаблонов с `is`</span><span class="sxs-lookup"><span data-stu-id="feadc-128">Pattern matching with `is`</span></span>

<span data-ttu-id="feadc-129">Начиная с C# 7.0 операторы `is` и [switch](../../../csharp/language-reference/keywords/switch.md) поддерживают сопоставление шаблонов.</span><span class="sxs-lookup"><span data-stu-id="feadc-129">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="feadc-130">Ключевое слово `is` поддерживает следующие шаблоны:</span><span class="sxs-lookup"><span data-stu-id="feadc-130">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="feadc-131">[Шаблон типа](#type), который проверяет, можно ли преобразовать выражение в указанный тип и, если можно, приводит его к переменной этого типа.</span><span class="sxs-lookup"><span data-stu-id="feadc-131">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="feadc-132">[Шаблон константы](#constant), который проверяет, получает ли выражение указанное постоянное значение.</span><span class="sxs-lookup"><span data-stu-id="feadc-132">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="feadc-133">[Шаблон переменной](#var) — совпадение всегда является успешным и привязывает значение выражения к новой локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="feadc-133">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <a name="a-nametype-type-pattern"></a><span data-ttu-id="feadc-134"><a name="type" />Шаблон типа</span><span class="sxs-lookup"><span data-stu-id="feadc-134"><a name="type" />Type pattern</span></span>

<span data-ttu-id="feadc-135">При использовании шаблона типа для сопоставления шаблонов `is` проверяет, можно ли преобразовать выражение в указанный тип и, если это возможно, приводит его к переменной этого типа.</span><span class="sxs-lookup"><span data-stu-id="feadc-135">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="feadc-136">Это простое расширение оператора `is` для краткого определения и преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="feadc-136">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="feadc-137">Шаблон типа `is` имеет следующий общий вид:</span><span class="sxs-lookup"><span data-stu-id="feadc-137">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="feadc-138">где *expr* — это выражение, значением которого является экземпляр какого-либо типа, *type* — это имя типа, в который должен быть преобразован результат *expr*, *varname* — это объект, в который преобразуется результат *expr*, если проверка `is` возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="feadc-138">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="feadc-139">Выражение `is` имеет значение `true`, если *expr* не имеет значение `null` и выполняется одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="feadc-139">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="feadc-140">*expr* представляет собой экземпляр того же типа, что и *type*;</span><span class="sxs-lookup"><span data-stu-id="feadc-140">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="feadc-141">*expr* является экземпляром типа, производного от *type*.</span><span class="sxs-lookup"><span data-stu-id="feadc-141">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="feadc-142">Другими словами, результат *expr* может быть приведен с повышением к экземпляру *type*.</span><span class="sxs-lookup"><span data-stu-id="feadc-142">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="feadc-143">*expr* имеет тип времени компиляции, который является базовым классом для *type*, и *expr* имеет тип среды выполнения, который является *type* или производным от *type*.</span><span class="sxs-lookup"><span data-stu-id="feadc-143">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="feadc-144">*Тип времени компиляции* переменной представляет собой тип переменной, как определено в объявлении.</span><span class="sxs-lookup"><span data-stu-id="feadc-144">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="feadc-145">*Тип среды выполнения* переменной представляет собой тип экземпляра, назначенный этой переменной.</span><span class="sxs-lookup"><span data-stu-id="feadc-145">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="feadc-146">*expr* является экземпляром типа, который реализует интерфейс *type*.</span><span class="sxs-lookup"><span data-stu-id="feadc-146">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="feadc-147">Начиная с версии C# 7.1, *expr* может иметь тип времени компиляции, определяемый параметром универсального типа и его ограничениями.</span><span class="sxs-lookup"><span data-stu-id="feadc-147">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span> 

<span data-ttu-id="feadc-148">Если *expr* имеет значение `true` и `is` используется с оператором `if`, назначается *varname*, который действует только в пределах оператора `if`.</span><span class="sxs-lookup"><span data-stu-id="feadc-148">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="feadc-149">В следующем примере используется шаблон типа `is`, который обеспечивает реализацию метода <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> типа.</span><span class="sxs-lookup"><span data-stu-id="feadc-149">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="feadc-150">Без сопоставления шаблонов этот код может быть написан следующим образом.</span><span class="sxs-lookup"><span data-stu-id="feadc-150">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="feadc-151">При использовании шаблона типа создается более лаконичный и удобочитаемый код, причем проверять результат преобразования (`null`) не требуется.</span><span class="sxs-lookup"><span data-stu-id="feadc-151">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="feadc-152">Шаблон типа `is` также позволяет создавать более компактный код при определении типа для типа значения.</span><span class="sxs-lookup"><span data-stu-id="feadc-152">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="feadc-153">В следующем примере используется шаблон типа `is`, чтобы определить, является ли объект экземпляром `Person` или `Dog` перед отображением значения соответствующего свойства.</span><span class="sxs-lookup"><span data-stu-id="feadc-153">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="feadc-154">Для эквивалентного кода без сопоставления шаблонов требуется отдельное назначение, которое включает явное приведение.</span><span class="sxs-lookup"><span data-stu-id="feadc-154">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="feadc-155"><a name="constant" /> Шаблон константы</span><span class="sxs-lookup"><span data-stu-id="feadc-155"><a name="constant" /> Constant pattern</span></span>

<span data-ttu-id="feadc-156">При выполнении сопоставления с шаблоном константы `is` проверяет, равно ли выражение указанной константе.</span><span class="sxs-lookup"><span data-stu-id="feadc-156">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="feadc-157">В C# 6 и более ранних версиях шаблон константы поддерживается оператором [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="feadc-157">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="feadc-158">Начиная с версии C# 7.0, также включена поддержка оператором `is`.</span><span class="sxs-lookup"><span data-stu-id="feadc-158">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="feadc-159">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="feadc-159">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="feadc-160">где *expr* — это выражение для вычисления, а *constant* — это значение, которое нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="feadc-160">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="feadc-161">*constant* может быть любой из следующих константных выражений:</span><span class="sxs-lookup"><span data-stu-id="feadc-161">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="feadc-162">литеральное значение;</span><span class="sxs-lookup"><span data-stu-id="feadc-162">A literal value.</span></span>

- <span data-ttu-id="feadc-163">имя объявленной переменной `const`;</span><span class="sxs-lookup"><span data-stu-id="feadc-163">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="feadc-164">константа перечисления.</span><span class="sxs-lookup"><span data-stu-id="feadc-164">An enumeration constant.</span></span>

<span data-ttu-id="feadc-165">Константное выражение вычисляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="feadc-165">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="feadc-166">Если *expr* и *constant* являются целочисленными типами, оператор равенства C# определяет, возвращает ли выражение `true` (то есть выполняется ли условие `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="feadc-166">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="feadc-167">В противном случае значение выражения определяется с помощью вызова статического метода [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="feadc-167">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="feadc-168">В следующем примере шаблон типа и шаблон константы объединяются для проверки того, является ли объект экземпляром `Dice` и, если это так, определяют, равно ли 6 значение броска кости.</span><span class="sxs-lookup"><span data-stu-id="feadc-168">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="feadc-169">Проверку значения `null` можно выполнять с использованием константного шаблона.</span><span class="sxs-lookup"><span data-stu-id="feadc-169">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="feadc-170">Ключевое слово `null` поддерживается оператором `is`.</span><span class="sxs-lookup"><span data-stu-id="feadc-170">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="feadc-171">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="feadc-171">Its syntax is:</span></span>

```csharp 
   expr is null
```

<span data-ttu-id="feadc-172">Следующий пример демонстрирует сравнение проверок `null`:</span><span class="sxs-lookup"><span data-stu-id="feadc-172">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <span data-ttu-id="feadc-173"><a name="var" /> Шаблон переменной </a></span><span class="sxs-lookup"><span data-stu-id="feadc-173"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="feadc-174">Шаблон `var` является универсальным и подходит для любых типов и значений.</span><span class="sxs-lookup"><span data-stu-id="feadc-174">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="feadc-175">Значение *expr* всегда назначается локальной переменной того же типа, что и тип времени компиляции *expr*.</span><span class="sxs-lookup"><span data-stu-id="feadc-175">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="feadc-176">Результат выражения `is` всегда равен `true`.</span><span class="sxs-lookup"><span data-stu-id="feadc-176">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="feadc-177">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="feadc-177">Its syntax is:</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="feadc-178">В следующем примере шаблон переменной используется для назначения выражения переменной с именем `obj`.</span><span class="sxs-lookup"><span data-stu-id="feadc-178">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="feadc-179">Затем отображается значение и тип `obj`.</span><span class="sxs-lookup"><span data-stu-id="feadc-179">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="feadc-180">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="feadc-180">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="feadc-181">См. также</span><span class="sxs-lookup"><span data-stu-id="feadc-181">See also</span></span>

- [<span data-ttu-id="feadc-182">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="feadc-182">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="feadc-183">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="feadc-183">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="feadc-184">typeof</span><span class="sxs-lookup"><span data-stu-id="feadc-184">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
- [<span data-ttu-id="feadc-185">as</span><span class="sxs-lookup"><span data-stu-id="feadc-185">as</span></span>](../../../csharp/language-reference/keywords/as.md)
- [<span data-ttu-id="feadc-186">Ключевые слова операторов</span><span class="sxs-lookup"><span data-stu-id="feadc-186">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
