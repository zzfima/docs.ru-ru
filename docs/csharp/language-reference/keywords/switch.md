---
title: "Ключевое слово switch (справочник по C#)"
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 387c8c7e44ab818ca97e686330746f50df091bb9
ms.openlocfilehash: 5c151e3bbd46212f1234d46ff05d389f2384ca0e
ms.contentlocale: ru-ru
ms.lasthandoff: 08/01/2017

---
# <a name="switch-c-reference"></a><span data-ttu-id="7447a-102">switch (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7447a-102">switch (C# Reference)</span></span>
<span data-ttu-id="7447a-103">`switch` — это оператор выбора, который выбирает для выполнения один *раздел switch* из списка кандидатов, сравнивая их с *выражением соответствия*.</span><span class="sxs-lookup"><span data-stu-id="7447a-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span> 
  
 <span data-ttu-id="7447a-104">[!code-cs[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-104">[!code-cs[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]</span></span>  

<span data-ttu-id="7447a-105">Оператор `switch` часто используется вместо конструкции [if-else](if-else.md), если одно выражение проверяется на соответствие трем или больше условиям.</span><span class="sxs-lookup"><span data-stu-id="7447a-105">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="7447a-106">Например, следующий оператор `switch` определяет, имеет ли переменная типа `Color` одно из трех значений:</span><span class="sxs-lookup"><span data-stu-id="7447a-106">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span> 

<span data-ttu-id="7447a-107">[!code-cs[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-107">[!code-cs[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]</span></span> 

<span data-ttu-id="7447a-108">Это эквивалентно следующему примеру, в котором используется конструкция `if` - `else`.</span><span class="sxs-lookup"><span data-stu-id="7447a-108">It is equivalent to the following example that uses an `if`-`else` construct.</span></span> 

<span data-ttu-id="7447a-109">[!code-cs[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-109">[!code-cs[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]</span></span> 

## <a name="the-match-expression"></a><span data-ttu-id="7447a-110">Выражение соответствия</span><span class="sxs-lookup"><span data-stu-id="7447a-110">The match expression</span></span>

<span data-ttu-id="7447a-111">Выражение соответствия предоставляет значение для сравнения в шаблонами в метках `case`.</span><span class="sxs-lookup"><span data-stu-id="7447a-111">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="7447a-112">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7447a-112">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="7447a-113">В C# 6 выражение соответствия должно быть выражением, возвращающим значение следующих типов:</span><span class="sxs-lookup"><span data-stu-id="7447a-113">In C# 6, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="7447a-114">[char](char.md);</span><span class="sxs-lookup"><span data-stu-id="7447a-114">a [char](char.md).</span></span>
- <span data-ttu-id="7447a-115">[string](string.md);</span><span class="sxs-lookup"><span data-stu-id="7447a-115">a [string](string.md).</span></span>
- <span data-ttu-id="7447a-116">[bool](bool.md);</span><span class="sxs-lookup"><span data-stu-id="7447a-116">a [bool](bool.md).</span></span> 
- <span data-ttu-id="7447a-117">целочисленное значение, например [int](int.md) или [long](long.md);</span><span class="sxs-lookup"><span data-stu-id="7447a-117">an integral value, such as an [int](int.md) or a [long](long.md).</span></span>
- <span data-ttu-id="7447a-118">значение [enum](enum.md).</span><span class="sxs-lookup"><span data-stu-id="7447a-118">an [enum](enum.md) value.</span></span>

<span data-ttu-id="7447a-119">Начиная с C# 7, выражение соответствия может быть любым выражением, отличным от NULL.</span><span class="sxs-lookup"><span data-stu-id="7447a-119">Starting with C# 7, the match expression can be any non-null expression.</span></span>
 
## <a name="the-switch-section"></a><span data-ttu-id="7447a-120">Раздел switch</span><span class="sxs-lookup"><span data-stu-id="7447a-120">The switch section</span></span>
 
 <span data-ttu-id="7447a-121">Оператор `switch` включает один или несколько разделов switch.</span><span class="sxs-lookup"><span data-stu-id="7447a-121">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="7447a-122">Каждый раздел switch содержит одну или несколько *меток case*, за которыми следует один или несколько операторов.</span><span class="sxs-lookup"><span data-stu-id="7447a-122">Each switch section contains one or more *case labels* followed by one or more statements.</span></span> <span data-ttu-id="7447a-123">В следующем примере показан простой оператор `switch` с тремя разделами switch.</span><span class="sxs-lookup"><span data-stu-id="7447a-123">The following example shows a simple `switch` statement that has three switch sections.</span></span> <span data-ttu-id="7447a-124">Каждый раздел switch содержит одну метку case, например `case 1:`, и два оператора.</span><span class="sxs-lookup"><span data-stu-id="7447a-124">Each switch section has one case label, such as `case 1:`, and two statements.</span></span>
 
  <span data-ttu-id="7447a-125">Оператор `switch` может содержать любое количество разделов switch, а каждый раздел может иметь одну или несколько меток case (как показано в следующем примере).</span><span class="sxs-lookup"><span data-stu-id="7447a-125">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="7447a-126">Однако две метки case не могут содержать одно и то же выражение.</span><span class="sxs-lookup"><span data-stu-id="7447a-126">However, no two case labels may contain the same expression.</span></span>  

 <span data-ttu-id="7447a-127">[!code-cs[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-127">[!code-cs[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]</span></span>  

 <span data-ttu-id="7447a-128">Выполняет только раздел switch в операторе switch.</span><span class="sxs-lookup"><span data-stu-id="7447a-128">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="7447a-129">C# не позволяет продолжить выполнение следующего раздела switch после выполнения предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="7447a-129">C# does not allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="7447a-130">В связи с этим приведенный ниже код создает ошибку компилятора CS0163: "Управление не может передаваться вниз от одной метки case (<case label>) к другой".</span><span class="sxs-lookup"><span data-stu-id="7447a-130">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (<case label>) to another."</span></span>   

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
<span data-ttu-id="7447a-131">Обычно для соблюдения этого требования выполняется явный выход из раздела switch с использованием оператора [break](break.md), [goto](goto.md) или [return](return.md).</span><span class="sxs-lookup"><span data-stu-id="7447a-131">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="7447a-132">При этом допустим также следующий код, поскольку он гарантирует, что управление программой не будет передано дальше, в раздел switch `default`.</span><span class="sxs-lookup"><span data-stu-id="7447a-132">However, the following code is also valid, because it ensures that program control cannot fall through to the `default` switch section.</span></span>
  
 <span data-ttu-id="7447a-133">[!code-cs[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-133">[!code-cs[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]</span></span>    
  
 <span data-ttu-id="7447a-134">Выполнение списка операторов в разделе switch с меткой case, соответствующей выражению сопоставления, начинается с первого оператора и продолжается по списку, обычно до достижения оператора перехода, такого как `break`, `goto case`, `goto label`, `return` или `throw`.</span><span class="sxs-lookup"><span data-stu-id="7447a-134">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="7447a-135">В этой точке управление передается за пределы оператора `switch` или к другой метке case.</span><span class="sxs-lookup"><span data-stu-id="7447a-135">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="7447a-136">Оператор `goto`, если он используется, должен передать управление константе типа метки.</span><span class="sxs-lookup"><span data-stu-id="7447a-136">A `goto` statement, if it is used, must transfer control to a constant label.</span></span> <span data-ttu-id="7447a-137">Это ограничение является обязательным, поскольку попытка передачи управления переменной типа метки может иметь нежелательные побочные эффекты, такие передача управления в непредусмотренное расположение в коде или создание бесконечного цикла.</span><span class="sxs-lookup"><span data-stu-id="7447a-137">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="7447a-138">Метки case</span><span class="sxs-lookup"><span data-stu-id="7447a-138">Case labels</span></span>

 <span data-ttu-id="7447a-139">Каждая метка case указывает на шаблон для сравнения с выражением сопоставления (переменная `caseSwitch` в предыдущем примере).</span><span class="sxs-lookup"><span data-stu-id="7447a-139">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="7447a-140">Если они совпадают, управление передается разделу switch, который содержит **первую** соответствующую метку case.</span><span class="sxs-lookup"><span data-stu-id="7447a-140">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="7447a-141">Если с выражением сопоставления не совпадает ни один шаблон метки case, управление передается разделу с меткой case `default` (если такой имеется).</span><span class="sxs-lookup"><span data-stu-id="7447a-141">If no case label pattern matches the match expression, control is transfered to the section with the `default` case label, if there is one.</span></span> <span data-ttu-id="7447a-142">Если метки case `default` нет, никакие операторы ни в одном из разделов switch не выполняются, а оператор `switch` теряет управление.</span><span class="sxs-lookup"><span data-stu-id="7447a-142">If there is no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

 <span data-ttu-id="7447a-143">Дополнительные сведения об операторе `switch` и сопоставлении шаблонов см. в разделе [Сопоставление шаблонов с оператором `switch`](#pattern).</span><span class="sxs-lookup"><span data-stu-id="7447a-143">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

 <span data-ttu-id="7447a-144">Поскольку C# 6 поддерживает только шаблон констант и не допускает повтор постоянных значений, метки case определяют взаимоисключающие значения, и выражению сопоставления может соответствовать только один шаблон.</span><span class="sxs-lookup"><span data-stu-id="7447a-144">Because C# 6 supports only the constant pattern and does not allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="7447a-145">В связи с этим порядок отображения операторов `case` не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="7447a-145">As a result, the order in which `case` statements appear is unimportant.</span></span>

 <span data-ttu-id="7447a-146">Тем не менее поскольку в C# 7 поддерживаются другие шаблоны, метки case не нужно определять как взаимоисключающие значения, и выражению соответствия могут соответствовать сразу несколько шаблонов.</span><span class="sxs-lookup"><span data-stu-id="7447a-146">In C# 7, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="7447a-147">Поскольку в разделе switch выполняются только те операторы, которые содержат первый совпадающий шаблон, порядок отображения операторов `case` становится важным.</span><span class="sxs-lookup"><span data-stu-id="7447a-147">Because only the statements in the switch section that contains the first matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="7447a-148">Обнаружив раздел switch, оператор или операторы которого эквивалентны предыдущим операторам или являются их подмножествами, C# выдает ошибку компилятора CS8120, "Метка case оператора switch уже обработана предыдущей меткой case".</span><span class="sxs-lookup"><span data-stu-id="7447a-148">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span> 

 <span data-ttu-id="7447a-149">В следующем примере демонстрируется оператор `switch` с использованием различных не взаимоисключающих шаблонов.</span><span class="sxs-lookup"><span data-stu-id="7447a-149">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="7447a-150">Если раздел switch `case 0:` перемещается и перестает быть первым разделом в операторе `switch`, C# выдает ошибку компилятора, поскольку целое число с нулевым значением представляет собой подмножество всех целых чисел — этот шаблон определен оператором `case int val`.</span><span class="sxs-lookup"><span data-stu-id="7447a-150">If you move the `case 0:` switch section so that it is no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

 <span data-ttu-id="7447a-151">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-151">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]</span></span>    

<span data-ttu-id="7447a-152">Устранить эту проблему и предупреждение компилятора можно одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="7447a-152">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="7447a-153">изменив порядок разделов switch;</span><span class="sxs-lookup"><span data-stu-id="7447a-153">By changing the order of the switch sections.</span></span> 
 
- <span data-ttu-id="7447a-154">вставив предложение </a name="when">when</a> в метку `case`.</span><span class="sxs-lookup"><span data-stu-id="7447a-154">By using a </a name="when">when clause</a> in the `case` label.</span></span>
 
## <a name="the-default-case"></a><span data-ttu-id="7447a-155">Метка case `default`</span><span class="sxs-lookup"><span data-stu-id="7447a-155">The `default` case</span></span>

<span data-ttu-id="7447a-156">Метка case `default` указывает на раздел switch, который будет выполнен, если выражение соответствия не совпадет ни с одной другой меткой `case`.</span><span class="sxs-lookup"><span data-stu-id="7447a-156">The `default` case specifies the switch section to execute if the match expression does not match any other `case` label.</span></span> <span data-ttu-id="7447a-157">Если метки case `default` нет, а выражение соответствия не совпадает ни с одной другой меткой `case`, выполнение программы передается оператору `switch`.</span><span class="sxs-lookup"><span data-stu-id="7447a-157">If a `default` case is not present and the match expression does not match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="7447a-158">Метка case `default` может отображаться в операторе `switch` в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="7447a-158">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="7447a-159">Она всегда оценивается последней, после оценки всех меток `case`, независимо от их порядка.</span><span class="sxs-lookup"><span data-stu-id="7447a-159">Regardless of its order in the source code, it is always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="7447a-160">Сопоставление шаблонов <a name="pattern" /> с оператором `switch`</span><span class="sxs-lookup"><span data-stu-id="7447a-160"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>
  
<span data-ttu-id="7447a-161">Каждый оператор `case` определяет шаблон, который в случае совпадения с выражением соответствия вызывает выполнение входящего в него раздела switch.</span><span class="sxs-lookup"><span data-stu-id="7447a-161">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="7447a-162">Шаблон константы поддерживают все версии C#.</span><span class="sxs-lookup"><span data-stu-id="7447a-162">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="7447a-163">Остальные шаблоны поддерживаются, начиная с C# 7.</span><span class="sxs-lookup"><span data-stu-id="7447a-163">The remaining patterns are supported beginning with C# 7.</span></span> 
  
### <a name="constant-pattern"></a><span data-ttu-id="7447a-164">Шаблон константы</span><span class="sxs-lookup"><span data-stu-id="7447a-164">Constant pattern</span></span> 

<span data-ttu-id="7447a-165">Шаблон константы проверяет, равно ли выражение указанной константе.</span><span class="sxs-lookup"><span data-stu-id="7447a-165">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="7447a-166">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7447a-166">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="7447a-167">здесь *constant* — это значение для проверки.</span><span class="sxs-lookup"><span data-stu-id="7447a-167">where *constant* is the value to test for.</span></span> <span data-ttu-id="7447a-168">Значением *constant* может быть любое из следующих константных выражений:</span><span class="sxs-lookup"><span data-stu-id="7447a-168">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="7447a-169">литерал [bool](bool.md), `true` или `false`;</span><span class="sxs-lookup"><span data-stu-id="7447a-169">A [bool](bool.md) literal, either `true` or `false`.</span></span>
- <span data-ttu-id="7447a-170">любой целочисленный тип, такой как [int](int.md), [long](long.md) или [byte](byte.md);</span><span class="sxs-lookup"><span data-stu-id="7447a-170">Any integral constant, such as an [int](int.md), a [long](long.md), or a [byte](byte.md).</span></span> 
- <span data-ttu-id="7447a-171">имя объявленной переменной `const`;</span><span class="sxs-lookup"><span data-stu-id="7447a-171">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="7447a-172">константа перечисления;</span><span class="sxs-lookup"><span data-stu-id="7447a-172">An enumeration constant.</span></span>
- <span data-ttu-id="7447a-173">литерал [char](char.md);</span><span class="sxs-lookup"><span data-stu-id="7447a-173">A [char](char.md) literal.</span></span>
- <span data-ttu-id="7447a-174">литерал [string](string.md).</span><span class="sxs-lookup"><span data-stu-id="7447a-174">A [string](string.md) literal.</span></span>

<span data-ttu-id="7447a-175">Константное выражение вычисляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7447a-175">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="7447a-176">Если *expr* и *constant* являются целочисленными типами, оператор равенства C# определяет, возвращает ли выражение `true` (то есть выполняется ли условие `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="7447a-176">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="7447a-177">В противном случае значение выражения определяется с помощью вызова статического метода [Object.Equals (expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="7447a-177">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="7447a-178">В следующем примере шаблон константы используется для того, чтобы определить, выпадает ли определенная дата на выходные, первый или последний рабочий день недели либо середину недели.</span><span class="sxs-lookup"><span data-stu-id="7447a-178">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="7447a-179">Он сравнивает свойство [DateTime.DayOfWeek](xref:System.DateTime.DayOfWeek) текущего дня с членами перечисления @System.DayOfWeek.</span><span class="sxs-lookup"><span data-stu-id="7447a-179">It evaluates the [DateTime.DayOfWeek](xref:System.DateTime.DayOfWeek) property of the current day against the members of the @System.DayOfWeek enumeration.</span></span> 

<span data-ttu-id="7447a-180">[!code-cs[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-180">[!code-cs[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]</span></span>

<span data-ttu-id="7447a-181">В следующем примере шаблон констант используется для обработки данных, введенных пользователем в консольное приложение, имитирующее кофейный автомат.</span><span class="sxs-lookup"><span data-stu-id="7447a-181">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>
  
 <span data-ttu-id="7447a-182">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]</span><span class="sxs-lookup"><span data-stu-id="7447a-182">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]</span></span>  

### <a name="type-pattern"></a><span data-ttu-id="7447a-183">Шаблон типа</span><span class="sxs-lookup"><span data-stu-id="7447a-183">Type pattern</span></span>

<span data-ttu-id="7447a-184">Шаблон типа обеспечивает точное определение и преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="7447a-184">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="7447a-185">При использовании оператора `switch` для сопоставления шаблонов он проверяет, можно ли преобразовать выражение в указанный тип и, если это возможно, приводит его к переменной этого типа.</span><span class="sxs-lookup"><span data-stu-id="7447a-185">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="7447a-186">Он имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7447a-186">Its syntax is:</span></span>

```csharp
   case type varname 
```
<span data-ttu-id="7447a-187">здесь *type* — это имя типа, в который должен быть преобразован результат *expr*, *varname* — это объект, в который преобразуется результат *expr*, если сопоставление завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="7447a-187">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> 

<span data-ttu-id="7447a-188">Выражение `case` имеет значение `true`, если выполняется одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="7447a-188">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="7447a-189">*expr* представляет собой экземпляр того же типа, что и *type*;</span><span class="sxs-lookup"><span data-stu-id="7447a-189">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="7447a-190">*expr* является экземпляром типа, производного от *type*.</span><span class="sxs-lookup"><span data-stu-id="7447a-190">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="7447a-191">Другими словами, результат *expr* может быть приведен с повышением к экземпляру *type*.</span><span class="sxs-lookup"><span data-stu-id="7447a-191">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="7447a-192">*expr* имеет тип времени компиляции, который является базовым классом для *type*, и *expr* имеет тип среды выполнения, который является *type* или производным от *type*.</span><span class="sxs-lookup"><span data-stu-id="7447a-192">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="7447a-193">*Тип времени компиляции* переменной представляет собой тип переменной, заданный в ее определении типа.</span><span class="sxs-lookup"><span data-stu-id="7447a-193">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="7447a-194">*Тип среды выполнения* переменной представляет собой тип экземпляра, назначенный этой переменной.</span><span class="sxs-lookup"><span data-stu-id="7447a-194">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="7447a-195">*expr* является экземпляром типа, который реализует интерфейс *type*.</span><span class="sxs-lookup"><span data-stu-id="7447a-195">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="7447a-196">Если case имеет значение true, *varname* присваивается определенным образом и получает локальную область в пределах раздела switch.</span><span class="sxs-lookup"><span data-stu-id="7447a-196">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="7447a-197">Обратите внимание на то, что `null` не соответствует типу.</span><span class="sxs-lookup"><span data-stu-id="7447a-197">Note that `null` does not match a type.</span></span> <span data-ttu-id="7447a-198">Для сопоставления `null` используйте следующую метку `case`:</span><span class="sxs-lookup"><span data-stu-id="7447a-198">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```
 
<span data-ttu-id="7447a-199">В следующем примере шаблон типа используется для предоставления сведений о различные видах коллекций типов.</span><span class="sxs-lookup"><span data-stu-id="7447a-199">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

<span data-ttu-id="7447a-200">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-200">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]</span></span>

<span data-ttu-id="7447a-201">Без сопоставления шаблонов этот код может быть написан следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7447a-201">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="7447a-202">При использовании шаблона типа создается более лаконичный и удобочитаемый код, причем проверять результат преобразования (`null`) или выполнять повторное приведение не требуется.</span><span class="sxs-lookup"><span data-stu-id="7447a-202">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>  

<span data-ttu-id="7447a-203">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-203">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]</span></span>

## <a name="the-case-statement-and-the-when-clause"></a><span data-ttu-id="7447a-204">Оператор `case` и предложение `when`</span><span class="sxs-lookup"><span data-stu-id="7447a-204">The `case` statement and the `when` clause</span></span>

<span data-ttu-id="7447a-205">Начиная с C# 7, операторы case не обязательно должны быть взаимоисключающими. В связи с этим можно добавить предложение `when`, определяющее дополнительное условие, которому должен соответствовать оператор case, чтобы иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="7447a-205">Starting with C# 7, because case statements need not be mutually exclusive, you can use add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="7447a-206">Предложение `when` может быть любым выражением, возвращающим логическое значение.</span><span class="sxs-lookup"><span data-stu-id="7447a-206">The `when` clause can be any expression that returns a Boolean value.</span></span> <span data-ttu-id="7447a-207">Чаще всего предложение `when` используется для того, чтобы запретить выполнение раздела switch, если выражение соответствия имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="7447a-207">One of the more common uses for the `when` clause is used to prevent a switch section from executing when the value of a match expression is `null`.</span></span> 

 <span data-ttu-id="7447a-208">В следующем примере определяется базовый класс `Shape`, класс `Rectangle`, производный от `Shape`, и класс `Square`, производный от `Rectangle`.</span><span class="sxs-lookup"><span data-stu-id="7447a-208">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="7447a-209">Предложение `when` используется в нем для того, чтобы `ShowShapeInfo` обрабатывал объект `Rectangle`, которому назначена такая же длина и ширина, как у объекта `Square`, даже если экземпляр для него не создается как объект `Square`.</span><span class="sxs-lookup"><span data-stu-id="7447a-209">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if is has not been instantiated as a `Square` object.</span></span> <span data-ttu-id="7447a-210">Метод не пытается отобразить сведения ни об объекте со значением `null`, ни о форме с нулевой областью.</span><span class="sxs-lookup"><span data-stu-id="7447a-210">The method does not attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span> 

<span data-ttu-id="7447a-211">[!code-cs[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7447a-211">[!code-cs[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]</span></span>
  
<span data-ttu-id="7447a-212">Обратите внимание на то, что предложение `when` в этом примере, проверяющее, имеет ли объект `Shape` значение `null`, не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7447a-212">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` does not execute.</span></span> <span data-ttu-id="7447a-213">Правильный шаблон пути для проверки на наличие значения `null` — `case null:`.</span><span class="sxs-lookup"><span data-stu-id="7447a-213">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7447a-214">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7447a-214">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7447a-215">См. также</span><span class="sxs-lookup"><span data-stu-id="7447a-215">See Also</span></span>  

 <span data-ttu-id="7447a-216">[Справочник по C#](../index.md) </span><span class="sxs-lookup"><span data-stu-id="7447a-216">[C# Reference](../index.md) </span></span>  
 <span data-ttu-id="7447a-217">[Руководство по программированию на C#](../../programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7447a-217">[C# Programming Guide](../../programming-guide/index.md) </span></span>  
 <span data-ttu-id="7447a-218">[Ключевые слова в C#](index.md) </span><span class="sxs-lookup"><span data-stu-id="7447a-218">[C# Keywords](index.md) </span></span>  
 <span data-ttu-id="7447a-219">[if-else](if-else.md) </span><span class="sxs-lookup"><span data-stu-id="7447a-219">[if-else](if-else.md) </span></span>  
 [<span data-ttu-id="7447a-220">Соответствие шаблону</span><span class="sxs-lookup"><span data-stu-id="7447a-220">Pattern Matching</span></span>](../../pattern-matching.md)   
 

 

