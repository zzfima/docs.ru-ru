---
title: is. Справочник по C#
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: e64b690482419963a92764b2c97a42dbb231fbfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398307"
---
# <a name="is-c-reference"></a><span data-ttu-id="3f187-102">is (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="3f187-102">is (C# Reference)</span></span>

<span data-ttu-id="3f187-103">Оператор `is` проверяет совместимость результата выражения с заданным типом или (начиная с C# 7.0) проверяет выражение на соответствие шаблону.</span><span class="sxs-lookup"><span data-stu-id="3f187-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="3f187-104">Сведения об операторе тестирования типов `is` см. в соответствующем [разделе](../operators/type-testing-and-cast.md#is-operator) статьи об [операторах приведения и тестирования типов](../operators/type-testing-and-cast.md).</span><span class="sxs-lookup"><span data-stu-id="3f187-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="3f187-105">Сопоставление шаблонов с `is`</span><span class="sxs-lookup"><span data-stu-id="3f187-105">Pattern matching with `is`</span></span>

<span data-ttu-id="3f187-106">Начиная с C# 7.0 операторы `is` и [switch](switch.md) поддерживают сопоставление шаблонов.</span><span class="sxs-lookup"><span data-stu-id="3f187-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="3f187-107">Ключевое слово `is` поддерживает следующие шаблоны:</span><span class="sxs-lookup"><span data-stu-id="3f187-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="3f187-108">[Шаблон типа](#type-pattern), который проверяет, можно ли преобразовать выражение в указанный тип и, если можно, приводит его к переменной этого типа.</span><span class="sxs-lookup"><span data-stu-id="3f187-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="3f187-109">[Шаблон константы](#constant-pattern), который проверяет, получает ли выражение указанное постоянное значение.</span><span class="sxs-lookup"><span data-stu-id="3f187-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="3f187-110">[Шаблон переменной](#var-pattern) — совпадение всегда является успешным и привязывает значение выражения к новой локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="3f187-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="3f187-111">Шаблон типа</span><span class="sxs-lookup"><span data-stu-id="3f187-111">Type pattern</span></span>

<span data-ttu-id="3f187-112">При использовании шаблона типа для сопоставления шаблонов `is` проверяет, можно ли преобразовать выражение в указанный тип и, если это возможно, приводит его к переменной этого типа.</span><span class="sxs-lookup"><span data-stu-id="3f187-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="3f187-113">Это простое расширение оператора `is` для краткого определения и преобразования типов.</span><span class="sxs-lookup"><span data-stu-id="3f187-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="3f187-114">Шаблон типа `is` имеет следующий общий вид:</span><span class="sxs-lookup"><span data-stu-id="3f187-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="3f187-115">Здесь *expr* — это выражение, значением которого является экземпляр какого-либо типа, *type* — это имя типа, в который должен быть преобразован результат *expr*, а *varname* — это объект, в который преобразуется результат *expr*, если проверка `is` возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="3f187-115">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="3f187-116">Выражение `is` имеет значение `true`, если *expr* не имеет значение `null` и выполняется одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="3f187-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="3f187-117">*expr* представляет собой экземпляр того же типа, что и *type*;</span><span class="sxs-lookup"><span data-stu-id="3f187-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="3f187-118">*expr* является экземпляром типа, производного от *type*.</span><span class="sxs-lookup"><span data-stu-id="3f187-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="3f187-119">Другими словами, результат *expr* может быть приведен с повышением к экземпляру *type*.</span><span class="sxs-lookup"><span data-stu-id="3f187-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="3f187-120">*expr* имеет тип времени компиляции, который является базовым классом для *type*, и *expr* имеет тип среды выполнения, который является *type* или производным от *type*.</span><span class="sxs-lookup"><span data-stu-id="3f187-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="3f187-121">*Тип времени компиляции* переменной представляет собой тип переменной, как определено в объявлении.</span><span class="sxs-lookup"><span data-stu-id="3f187-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="3f187-122">*Тип среды выполнения* переменной представляет собой тип экземпляра, назначенный этой переменной.</span><span class="sxs-lookup"><span data-stu-id="3f187-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="3f187-123">*expr* является экземпляром типа, который реализует интерфейс *type*.</span><span class="sxs-lookup"><span data-stu-id="3f187-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="3f187-124">Начиная с версии C# 7.1, *expr* может иметь тип времени компиляции, определяемый параметром универсального типа и его ограничениями.</span><span class="sxs-lookup"><span data-stu-id="3f187-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="3f187-125">Если *expr* — `true` и `is` используется с инструкцией `if`, *varname* назначается только в пределах инструкции `if`.</span><span class="sxs-lookup"><span data-stu-id="3f187-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="3f187-126">Область видимости *varname* — от выражения `is` до конца блока, включающего инструкцию `if`.</span><span class="sxs-lookup"><span data-stu-id="3f187-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="3f187-127">Использование *varname* в любом другом месте вызовет ошибку во время компиляции из-за использования переменной, которая не была назначена.</span><span class="sxs-lookup"><span data-stu-id="3f187-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="3f187-128">В следующем примере используется шаблон типа `is`, который обеспечивает реализацию метода <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> типа.</span><span class="sxs-lookup"><span data-stu-id="3f187-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="3f187-129">Без сопоставления шаблонов этот код может быть написан следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3f187-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="3f187-130">При использовании шаблона типа создается более лаконичный и удобочитаемый код, причем проверять результат преобразования (`null`) не требуется.</span><span class="sxs-lookup"><span data-stu-id="3f187-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="3f187-131">Шаблон типа `is` также позволяет создавать более компактный код при определении типа для типа значения.</span><span class="sxs-lookup"><span data-stu-id="3f187-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="3f187-132">В следующем примере используется шаблон типа `is`, чтобы определить, является ли объект экземпляром `Person` или `Dog` перед отображением значения соответствующего свойства.</span><span class="sxs-lookup"><span data-stu-id="3f187-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="3f187-133">Для эквивалентного кода без сопоставления шаблонов требуется отдельное назначение, которое включает явное приведение.</span><span class="sxs-lookup"><span data-stu-id="3f187-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="3f187-134">Шаблон константы</span><span class="sxs-lookup"><span data-stu-id="3f187-134">Constant pattern</span></span>

<span data-ttu-id="3f187-135">При выполнении сопоставления с шаблоном константы `is` проверяет, равно ли выражение указанной константе.</span><span class="sxs-lookup"><span data-stu-id="3f187-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="3f187-136">В C# 6 и более ранних версиях шаблон константы поддерживается оператором [switch](switch.md).</span><span class="sxs-lookup"><span data-stu-id="3f187-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="3f187-137">Начиная с версии C# 7.0, также включена поддержка оператором `is`.</span><span class="sxs-lookup"><span data-stu-id="3f187-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="3f187-138">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3f187-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="3f187-139">где *expr* — это выражение для вычисления, а *constant* — это значение, которое нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="3f187-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="3f187-140">*constant* может быть любой из следующих константных выражений:</span><span class="sxs-lookup"><span data-stu-id="3f187-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="3f187-141">литеральное значение;</span><span class="sxs-lookup"><span data-stu-id="3f187-141">A literal value.</span></span>

- <span data-ttu-id="3f187-142">имя объявленной переменной `const`;</span><span class="sxs-lookup"><span data-stu-id="3f187-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="3f187-143">константа перечисления.</span><span class="sxs-lookup"><span data-stu-id="3f187-143">An enumeration constant.</span></span>

<span data-ttu-id="3f187-144">Константное выражение вычисляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3f187-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="3f187-145">Если *expr* и *constant* являются целочисленными типами, оператор равенства C# определяет, возвращает ли выражение `true` (то есть выполняется ли условие `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="3f187-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="3f187-146">В противном случае значение выражения определяется с помощью вызова статического метода [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="3f187-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="3f187-147">В следующем примере шаблон типа и шаблон константы объединяются для проверки того, является ли объект экземпляром `Dice` и, если это так, определяют, равно ли 6 значение броска кости.</span><span class="sxs-lookup"><span data-stu-id="3f187-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="3f187-148">Проверку значения `null` можно выполнять с использованием константного шаблона.</span><span class="sxs-lookup"><span data-stu-id="3f187-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="3f187-149">Ключевое слово `null` поддерживается оператором `is`.</span><span class="sxs-lookup"><span data-stu-id="3f187-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="3f187-150">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3f187-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="3f187-151">Следующий пример демонстрирует сравнение проверок `null`:</span><span class="sxs-lookup"><span data-stu-id="3f187-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="3f187-152">Шаблон var</span><span class="sxs-lookup"><span data-stu-id="3f187-152">var pattern</span></span>

<span data-ttu-id="3f187-153">Сопоставление шаблону `var` всегда завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="3f187-153">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="3f187-154">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3f187-154">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="3f187-155">Здесь значение *expr* всегда назначается локальной переменной с именем *varname*.</span><span class="sxs-lookup"><span data-stu-id="3f187-155">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="3f187-156">*varname* — это переменная, тип которой совпадает с типом времени компиляции для *expr*.</span><span class="sxs-lookup"><span data-stu-id="3f187-156">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="3f187-157">Если *expr* принимает значение `null`, выражение `is` возвращает значение `true` и присваивает переменной *varname* значение `null`.</span><span class="sxs-lookup"><span data-stu-id="3f187-157">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="3f187-158">Шаблон var является одним из немногих способов применения выражения `is`, при котором возвращается `true` для значения `null`.</span><span class="sxs-lookup"><span data-stu-id="3f187-158">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="3f187-159">Шаблон `var` можно использовать для создания временной переменной в логическом выражении, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3f187-159">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="3f187-160">В предыдущем примере временная переменная используется для хранения результатов ресурсоемкой операции.</span><span class="sxs-lookup"><span data-stu-id="3f187-160">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="3f187-161">Эту переменную можно использовать несколько раз.</span><span class="sxs-lookup"><span data-stu-id="3f187-161">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3f187-162">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="3f187-162">C# language specification</span></span>
  
<span data-ttu-id="3f187-163">Подробные сведения см. в разделе [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) (Оператор is) [спецификации языка C#](~/_csharplang/spec/introduction.md) и в следующих предложениях для языка C#:</span><span class="sxs-lookup"><span data-stu-id="3f187-163">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="3f187-164">Сопоставление шаблонов</span><span class="sxs-lookup"><span data-stu-id="3f187-164">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="3f187-165">Сопоставление шаблонов с универсальными шаблонами</span><span class="sxs-lookup"><span data-stu-id="3f187-165">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="3f187-166">См. также</span><span class="sxs-lookup"><span data-stu-id="3f187-166">See also</span></span>

- [<span data-ttu-id="3f187-167">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="3f187-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3f187-168">Ключевые слова C#</span><span class="sxs-lookup"><span data-stu-id="3f187-168">C# keywords</span></span>](index.md)
- [<span data-ttu-id="3f187-169">Операторы приведения и тестирования типов</span><span class="sxs-lookup"><span data-stu-id="3f187-169">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
