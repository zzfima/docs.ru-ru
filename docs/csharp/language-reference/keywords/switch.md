---
title: Ключевое слово switch (справочник по C#)
ms.date: 03/07/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6506278edb782f61b83cecfccba3126282c0ecf8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="switch-c-reference"></a><span data-ttu-id="50ff8-102">switch (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="50ff8-102">switch (C# Reference)</span></span>
<span data-ttu-id="50ff8-103">`switch` — это оператор выбора, который выбирает для выполнения один *раздел switch* из списка кандидатов, сравнивая их с *выражением соответствия*.</span><span class="sxs-lookup"><span data-stu-id="50ff8-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span> 
  
 [!code-csharp[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]  

<span data-ttu-id="50ff8-104">Оператор `switch` часто используется вместо конструкции [if-else](if-else.md), если одно выражение проверяется на соответствие трем или больше условиям.</span><span class="sxs-lookup"><span data-stu-id="50ff8-104">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="50ff8-105">Например, следующий оператор `switch` определяет, имеет ли переменная типа `Color` одно из трех значений:</span><span class="sxs-lookup"><span data-stu-id="50ff8-105">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span> 

[!code-csharp[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)] 

<span data-ttu-id="50ff8-106">Это эквивалентно следующему примеру, в котором используется конструкция `if` - `else`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-106">It is equivalent to the following example that uses an `if`-`else` construct.</span></span> 

[!code-csharp[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)] 

## <a name="the-match-expression"></a><span data-ttu-id="50ff8-107">Выражение соответствия</span><span class="sxs-lookup"><span data-stu-id="50ff8-107">The match expression</span></span>

<span data-ttu-id="50ff8-108">Выражение соответствия предоставляет значение для сравнения в шаблонами в метках `case`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-108">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="50ff8-109">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="50ff8-109">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="50ff8-110">В C# 6 выражение соответствия должно быть выражением, возвращающим значение следующих типов:</span><span class="sxs-lookup"><span data-stu-id="50ff8-110">In C# 6, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="50ff8-111">[char](char.md);</span><span class="sxs-lookup"><span data-stu-id="50ff8-111">a [char](char.md).</span></span>
- <span data-ttu-id="50ff8-112">[string](string.md);</span><span class="sxs-lookup"><span data-stu-id="50ff8-112">a [string](string.md).</span></span>
- <span data-ttu-id="50ff8-113">[bool](bool.md);</span><span class="sxs-lookup"><span data-stu-id="50ff8-113">a [bool](bool.md).</span></span> 
- <span data-ttu-id="50ff8-114">целочисленное значение, например [int](int.md) или [long](long.md);</span><span class="sxs-lookup"><span data-stu-id="50ff8-114">an integral value, such as an [int](int.md) or a [long](long.md).</span></span>
- <span data-ttu-id="50ff8-115">значение [enum](enum.md).</span><span class="sxs-lookup"><span data-stu-id="50ff8-115">an [enum](enum.md) value.</span></span>

<span data-ttu-id="50ff8-116">Начиная с C# 7.0 выражение соответствия может быть любым выражением, отличным от NULL.</span><span class="sxs-lookup"><span data-stu-id="50ff8-116">Starting with C# 7.0, the match expression can be any non-null expression.</span></span>
 
## <a name="the-switch-section"></a><span data-ttu-id="50ff8-117">Раздел switch</span><span class="sxs-lookup"><span data-stu-id="50ff8-117">The switch section</span></span>
 
 <span data-ttu-id="50ff8-118">Оператор `switch` включает один или несколько разделов switch.</span><span class="sxs-lookup"><span data-stu-id="50ff8-118">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="50ff8-119">Каждый раздел switch содержит одну или несколько *меток case*, за которыми следует один или несколько операторов.</span><span class="sxs-lookup"><span data-stu-id="50ff8-119">Each switch section contains one or more *case labels* followed by one or more statements.</span></span> <span data-ttu-id="50ff8-120">В следующем примере показан простой оператор `switch` с тремя разделами switch.</span><span class="sxs-lookup"><span data-stu-id="50ff8-120">The following example shows a simple `switch` statement that has three switch sections.</span></span> <span data-ttu-id="50ff8-121">Каждый раздел switch содержит одну метку case, например `case 1:`, и два оператора.</span><span class="sxs-lookup"><span data-stu-id="50ff8-121">Each switch section has one case label, such as `case 1:`, and two statements.</span></span>
 
  <span data-ttu-id="50ff8-122">Оператор `switch` может содержать любое количество разделов switch, а каждый раздел может иметь одну или несколько меток case (как показано в следующем примере).</span><span class="sxs-lookup"><span data-stu-id="50ff8-122">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="50ff8-123">Однако две метки case не могут содержать одно и то же выражение.</span><span class="sxs-lookup"><span data-stu-id="50ff8-123">However, no two case labels may contain the same expression.</span></span>  

 [!code-csharp[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]  

 <span data-ttu-id="50ff8-124">Выполняет только раздел switch в операторе switch.</span><span class="sxs-lookup"><span data-stu-id="50ff8-124">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="50ff8-125">C# не позволяет продолжить выполнение следующего раздела switch после выполнения предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="50ff8-125">C# does not allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="50ff8-126">В связи с этим приведенный ниже код создает ошибку компилятора CS0163: "Управление не может передаваться вниз от одной метки case (<case label>) к другой".</span><span class="sxs-lookup"><span data-stu-id="50ff8-126">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (<case label>) to another."</span></span>  

```csharp  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
<span data-ttu-id="50ff8-127">Обычно для соблюдения этого требования выполняется явный выход из раздела switch с использованием оператора [break](break.md), [goto](goto.md) или [return](return.md).</span><span class="sxs-lookup"><span data-stu-id="50ff8-127">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="50ff8-128">При этом допустим также следующий код, поскольку он гарантирует, что управление программой не будет передано дальше, в раздел switch `default`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-128">However, the following code is also valid, because it ensures that program control cannot fall through to the `default` switch section.</span></span>
  
 [!code-csharp[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]    
  
 <span data-ttu-id="50ff8-129">Выполнение списка операторов в разделе switch с меткой case, соответствующей выражению сопоставления, начинается с первого оператора и продолжается по списку, обычно до достижения оператора перехода, такого как `break`, `goto case`, `goto label`, `return` или `throw`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-129">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="50ff8-130">В этой точке управление передается за пределы оператора `switch` или к другой метке case.</span><span class="sxs-lookup"><span data-stu-id="50ff8-130">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="50ff8-131">Оператор `goto`, если он используется, должен передать управление константе типа метки.</span><span class="sxs-lookup"><span data-stu-id="50ff8-131">A `goto` statement, if it is used, must transfer control to a constant label.</span></span> <span data-ttu-id="50ff8-132">Это ограничение является обязательным, поскольку попытка передачи управления переменной типа метки может иметь нежелательные побочные эффекты, такие передача управления в непредусмотренное расположение в коде или создание бесконечного цикла.</span><span class="sxs-lookup"><span data-stu-id="50ff8-132">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="50ff8-133">Метки case</span><span class="sxs-lookup"><span data-stu-id="50ff8-133">Case labels</span></span>

 <span data-ttu-id="50ff8-134">Каждая метка case указывает на шаблон для сравнения с выражением сопоставления (переменная `caseSwitch` в предыдущем примере).</span><span class="sxs-lookup"><span data-stu-id="50ff8-134">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="50ff8-135">Если они совпадают, управление передается разделу switch, который содержит **первую** соответствующую метку case.</span><span class="sxs-lookup"><span data-stu-id="50ff8-135">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="50ff8-136">Если с выражением соответствия не совпадает ни один шаблон метки case, управление передается разделу с меткой case `default`, если такой раздел существует.</span><span class="sxs-lookup"><span data-stu-id="50ff8-136">If no case label pattern matches the match expression, control is transferred to the section with the `default` case label, if there is one.</span></span> <span data-ttu-id="50ff8-137">Если метки case `default` нет, никакие операторы ни в одном из разделов switch не выполняются, а оператор `switch` теряет управление.</span><span class="sxs-lookup"><span data-stu-id="50ff8-137">If there is no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

 <span data-ttu-id="50ff8-138">Дополнительные сведения об операторе `switch` и сопоставлении шаблонов см. в разделе [Сопоставление шаблонов с оператором `switch`](#pattern).</span><span class="sxs-lookup"><span data-stu-id="50ff8-138">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

 <span data-ttu-id="50ff8-139">Поскольку C# 6 поддерживает только шаблон констант и не допускает повтор постоянных значений, метки case определяют взаимоисключающие значения, и выражению сопоставления может соответствовать только один шаблон.</span><span class="sxs-lookup"><span data-stu-id="50ff8-139">Because C# 6 supports only the constant pattern and does not allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="50ff8-140">В связи с этим порядок отображения операторов `case` не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="50ff8-140">As a result, the order in which `case` statements appear is unimportant.</span></span>

 <span data-ttu-id="50ff8-141">Тем не менее, поскольку в C# 7.0 поддерживаются другие шаблоны, метки case не нужно определять как взаимоисключающие значения, и выражению соответствия могут соответствовать сразу несколько шаблонов.</span><span class="sxs-lookup"><span data-stu-id="50ff8-141">In C# 7.0, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="50ff8-142">Поскольку в разделе switch выполняются только те операторы, которые содержат первый совпадающий шаблон, порядок отображения операторов `case` становится важным.</span><span class="sxs-lookup"><span data-stu-id="50ff8-142">Because only the statements in the switch section that contains the first matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="50ff8-143">Обнаружив раздел switch, оператор или операторы которого эквивалентны предыдущим операторам или являются их подмножествами, C# выдает ошибку компилятора CS8120, "Метка case оператора switch уже обработана предыдущей меткой case".</span><span class="sxs-lookup"><span data-stu-id="50ff8-143">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span> 

 <span data-ttu-id="50ff8-144">В следующем примере демонстрируется оператор `switch` с использованием различных не взаимоисключающих шаблонов.</span><span class="sxs-lookup"><span data-stu-id="50ff8-144">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="50ff8-145">Если раздел switch `case 0:` перемещается и перестает быть первым разделом в операторе `switch`, C# выдает ошибку компилятора, поскольку целое число с нулевым значением представляет собой подмножество всех целых чисел — этот шаблон определен оператором `case int val`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-145">If you move the `case 0:` switch section so that it is no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

 [!code-csharp[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]    

<span data-ttu-id="50ff8-146">Устранить эту проблему и предупреждение компилятора можно одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="50ff8-146">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="50ff8-147">изменив порядок разделов switch;</span><span class="sxs-lookup"><span data-stu-id="50ff8-147">By changing the order of the switch sections.</span></span> 
 
- <span data-ttu-id="50ff8-148">вставив предложение </a name="when">when</a> в метку `case`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-148">By using a </a name="when">when clause</a> in the `case` label.</span></span>
 
## <a name="the-default-case"></a><span data-ttu-id="50ff8-149">Метка case `default`</span><span class="sxs-lookup"><span data-stu-id="50ff8-149">The `default` case</span></span>

<span data-ttu-id="50ff8-150">Метка case `default` указывает на раздел switch, который будет выполнен, если выражение соответствия не совпадет ни с одной другой меткой `case`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-150">The `default` case specifies the switch section to execute if the match expression does not match any other `case` label.</span></span> <span data-ttu-id="50ff8-151">Если метки case `default` нет, а выражение соответствия не совпадает ни с одной другой меткой `case`, выполнение программы передается оператору `switch`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-151">If a `default` case is not present and the match expression does not match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="50ff8-152">Метка case `default` может отображаться в операторе `switch` в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="50ff8-152">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="50ff8-153">Она всегда оценивается последней, после оценки всех меток `case`, независимо от их порядка.</span><span class="sxs-lookup"><span data-stu-id="50ff8-153">Regardless of its order in the source code, it is always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="50ff8-154">Сопоставление шаблонов <a name="pattern" /> с оператором `switch`</span><span class="sxs-lookup"><span data-stu-id="50ff8-154"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>
  
<span data-ttu-id="50ff8-155">Каждый оператор `case` определяет шаблон, который в случае совпадения с выражением соответствия вызывает выполнение входящего в него раздела switch.</span><span class="sxs-lookup"><span data-stu-id="50ff8-155">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="50ff8-156">Шаблон константы поддерживают все версии C#.</span><span class="sxs-lookup"><span data-stu-id="50ff8-156">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="50ff8-157">Остальные шаблоны поддерживаются начиная с C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="50ff8-157">The remaining patterns are supported beginning with C# 7.0.</span></span> 
  
### <a name="constant-pattern"></a><span data-ttu-id="50ff8-158">Шаблон константы</span><span class="sxs-lookup"><span data-stu-id="50ff8-158">Constant pattern</span></span> 

<span data-ttu-id="50ff8-159">Шаблон константы проверяет, равно ли выражение указанной константе.</span><span class="sxs-lookup"><span data-stu-id="50ff8-159">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="50ff8-160">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="50ff8-160">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="50ff8-161">здесь *constant* — это значение для проверки.</span><span class="sxs-lookup"><span data-stu-id="50ff8-161">where *constant* is the value to test for.</span></span> <span data-ttu-id="50ff8-162">Значением *constant* может быть любое из следующих константных выражений:</span><span class="sxs-lookup"><span data-stu-id="50ff8-162">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="50ff8-163">литерал [bool](bool.md), `true` или `false`;</span><span class="sxs-lookup"><span data-stu-id="50ff8-163">A [bool](bool.md) literal, either `true` or `false`.</span></span>
- <span data-ttu-id="50ff8-164">любой целочисленный тип, такой как [int](int.md), [long](long.md) или [byte](byte.md);</span><span class="sxs-lookup"><span data-stu-id="50ff8-164">Any integral constant, such as an [int](int.md), a [long](long.md), or a [byte](byte.md).</span></span> 
- <span data-ttu-id="50ff8-165">имя объявленной переменной `const`;</span><span class="sxs-lookup"><span data-stu-id="50ff8-165">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="50ff8-166">константа перечисления;</span><span class="sxs-lookup"><span data-stu-id="50ff8-166">An enumeration constant.</span></span>
- <span data-ttu-id="50ff8-167">литерал [char](char.md);</span><span class="sxs-lookup"><span data-stu-id="50ff8-167">A [char](char.md) literal.</span></span>
- <span data-ttu-id="50ff8-168">литерал [string](string.md).</span><span class="sxs-lookup"><span data-stu-id="50ff8-168">A [string](string.md) literal.</span></span>

<span data-ttu-id="50ff8-169">Константное выражение вычисляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="50ff8-169">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="50ff8-170">Если *expr* и *constant* являются целочисленными типами, оператор равенства C# определяет, возвращает ли выражение `true` (то есть выполняется ли условие `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="50ff8-170">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="50ff8-171">В противном случае значение выражения определяется с помощью вызова статического метода [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="50ff8-171">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="50ff8-172">В следующем примере шаблон константы используется для того, чтобы определить, выпадает ли определенная дата на выходные, первый или последний рабочий день недели либо середину недели.</span><span class="sxs-lookup"><span data-stu-id="50ff8-172">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="50ff8-173">Он сравнивает свойство <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> текущего дня с членами перечисления <xref:System.DayOfWeek>.</span><span class="sxs-lookup"><span data-stu-id="50ff8-173">It evaluates the <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> property of the current day against the members of the <xref:System.DayOfWeek> enumeration.</span></span> 

[!code-csharp[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

<span data-ttu-id="50ff8-174">В следующем примере шаблон констант используется для обработки данных, введенных пользователем в консольное приложение, имитирующее кофейный автомат.</span><span class="sxs-lookup"><span data-stu-id="50ff8-174">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>
  
 [!code-csharp[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]  

### <a name="type-pattern"></a><span data-ttu-id="50ff8-175">Шаблон типа</span><span class="sxs-lookup"><span data-stu-id="50ff8-175">Type pattern</span></span>

<span data-ttu-id="50ff8-176">Шаблон типа обеспечивает точное определение и преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="50ff8-176">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="50ff8-177">При использовании оператора `switch` для сопоставления шаблонов он проверяет, можно ли преобразовать выражение в указанный тип и, если это возможно, приводит его к переменной этого типа.</span><span class="sxs-lookup"><span data-stu-id="50ff8-177">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="50ff8-178">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="50ff8-178">Its syntax is:</span></span>

```csharp
   case type varname 
```
<span data-ttu-id="50ff8-179">здесь *type* — это имя типа, в который должен быть преобразован результат *expr*, *varname* — это объект, в который преобразуется результат *expr*, если сопоставление завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="50ff8-179">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> 

<span data-ttu-id="50ff8-180">Выражение `case` имеет значение `true`, если выполняется одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="50ff8-180">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="50ff8-181">*expr* представляет собой экземпляр того же типа, что и *type*;</span><span class="sxs-lookup"><span data-stu-id="50ff8-181">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="50ff8-182">*expr* является экземпляром типа, производного от *type*.</span><span class="sxs-lookup"><span data-stu-id="50ff8-182">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="50ff8-183">Другими словами, результат *expr* может быть приведен с повышением к экземпляру *type*.</span><span class="sxs-lookup"><span data-stu-id="50ff8-183">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="50ff8-184">*expr* имеет тип времени компиляции, который является базовым классом для *type*, и *expr* имеет тип среды выполнения, который является *type* или производным от *type*.</span><span class="sxs-lookup"><span data-stu-id="50ff8-184">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="50ff8-185">*Тип времени компиляции* переменной представляет собой тип переменной, заданный в ее определении типа.</span><span class="sxs-lookup"><span data-stu-id="50ff8-185">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="50ff8-186">*Тип среды выполнения* переменной представляет собой тип экземпляра, назначенный этой переменной.</span><span class="sxs-lookup"><span data-stu-id="50ff8-186">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="50ff8-187">*expr* является экземпляром типа, который реализует интерфейс *type*.</span><span class="sxs-lookup"><span data-stu-id="50ff8-187">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="50ff8-188">Если case имеет значение true, *varname* присваивается определенным образом и получает локальную область в пределах раздела switch.</span><span class="sxs-lookup"><span data-stu-id="50ff8-188">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="50ff8-189">Обратите внимание на то, что `null` не соответствует типу.</span><span class="sxs-lookup"><span data-stu-id="50ff8-189">Note that `null` does not match a type.</span></span> <span data-ttu-id="50ff8-190">Для сопоставления `null` используйте следующую метку `case`:</span><span class="sxs-lookup"><span data-stu-id="50ff8-190">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```
 
<span data-ttu-id="50ff8-191">В следующем примере шаблон типа используется для предоставления сведений о различные видах коллекций типов.</span><span class="sxs-lookup"><span data-stu-id="50ff8-191">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

[!code-csharp[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

<span data-ttu-id="50ff8-192">Без сопоставления шаблонов этот код может быть написан следующим образом.</span><span class="sxs-lookup"><span data-stu-id="50ff8-192">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="50ff8-193">При использовании шаблона типа создается более лаконичный и удобочитаемый код, причем проверять результат преобразования (`null`) или выполнять повторное приведение не требуется.</span><span class="sxs-lookup"><span data-stu-id="50ff8-193">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>  

[!code-csharp[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="the-case-statement-and-the-when-clause"></a><span data-ttu-id="50ff8-194">Оператор `case` и предложение `when`</span><span class="sxs-lookup"><span data-stu-id="50ff8-194">The `case` statement and the `when` clause</span></span>

<span data-ttu-id="50ff8-195">Начиная с C# 7.0 операторы case необязательно должны быть взаимоисключающими. В связи с этим можно добавить предложение `when`, определяющее дополнительное условие, которому должен соответствовать оператор case, чтобы иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="50ff8-195">Starting with C# 7.0, because case statements need not be mutually exclusive, you can use add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="50ff8-196">Предложение `when` может быть любым выражением, возвращающим логическое значение.</span><span class="sxs-lookup"><span data-stu-id="50ff8-196">The `when` clause can be any expression that returns a Boolean value.</span></span> <span data-ttu-id="50ff8-197">Чаще всего предложение `when` используется для того, чтобы запретить выполнение раздела switch, если выражение соответствия имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-197">One of the more common uses for the `when` clause is used to prevent a switch section from executing when the value of a match expression is `null`.</span></span> 

 <span data-ttu-id="50ff8-198">В следующем примере определяется базовый класс `Shape`, класс `Rectangle`, производный от `Shape`, и класс `Square`, производный от `Rectangle`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-198">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="50ff8-199">Предложение `when` используется в нем для того, чтобы `ShowShapeInfo` обрабатывал объект `Rectangle`, которому назначена такая же длина и ширина, как у объекта `Square`, даже если экземпляр для него не создается как объект `Square`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-199">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if is has not been instantiated as a `Square` object.</span></span> <span data-ttu-id="50ff8-200">Метод не пытается отобразить сведения ни об объекте со значением `null`, ни о форме с нулевой областью.</span><span class="sxs-lookup"><span data-stu-id="50ff8-200">The method does not attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span> 

[!code-csharp[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]
  
<span data-ttu-id="50ff8-201">Обратите внимание на то, что предложение `when` в этом примере, проверяющее, имеет ли объект `Shape` значение `null`, не выполняется.</span><span class="sxs-lookup"><span data-stu-id="50ff8-201">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` does not execute.</span></span> <span data-ttu-id="50ff8-202">Правильный шаблон пути для проверки на наличие значения `null` — `case null:`.</span><span class="sxs-lookup"><span data-stu-id="50ff8-202">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="50ff8-203">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="50ff8-203">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](../../../../includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="50ff8-204">См. также</span><span class="sxs-lookup"><span data-stu-id="50ff8-204">See Also</span></span>  

 [<span data-ttu-id="50ff8-205">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="50ff8-205">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="50ff8-206">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="50ff8-206">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="50ff8-207">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="50ff8-207">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="50ff8-208">if-else</span><span class="sxs-lookup"><span data-stu-id="50ff8-208">if-else</span></span>](if-else.md)  
 [<span data-ttu-id="50ff8-209">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="50ff8-209">Pattern Matching</span></span>](../../pattern-matching.md)  
 

 
