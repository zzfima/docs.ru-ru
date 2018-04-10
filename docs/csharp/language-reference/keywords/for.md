---
title: for (Справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cb7e83733fe026658f502b430975a0f8a27e9df3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="for-c-reference"></a><span data-ttu-id="8710b-102">for (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8710b-102">for (C# Reference)</span></span>
<span data-ttu-id="8710b-103">Используя цикл `for`, можно раз за разом выполнять оператор или блок операторов, пока определенное выражение не примет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8710b-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="8710b-104">Этот тип цикла удобен для перебора массивов и для других сфер применения, в которых заранее известно количество итераций цикла.</span><span class="sxs-lookup"><span data-stu-id="8710b-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8710b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8710b-105">Example</span></span>  
 <span data-ttu-id="8710b-106">В следующем примере значение `i` записывается в консоль и увеличивается на единицу при каждой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="8710b-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 <span data-ttu-id="8710b-107">Оператор `for` в предыдущем примере выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8710b-107">The `for` statement in the previous example performs the following actions.</span></span>  
  
1.  <span data-ttu-id="8710b-108">Во-первых, устанавливается начальное значение переменной `i`.</span><span class="sxs-lookup"><span data-stu-id="8710b-108">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="8710b-109">Это происходит только один раз, независимо от числа повторений цикла.</span><span class="sxs-lookup"><span data-stu-id="8710b-109">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="8710b-110">Можно представить эту инициализацию происходящей вне циклического процесса.</span><span class="sxs-lookup"><span data-stu-id="8710b-110">You can think of this initialization as happening outside the looping process.</span></span>  
  
2.  <span data-ttu-id="8710b-111">Для вычисления условия (`i <= 5`) значение `i` сравнивается с 5.</span><span class="sxs-lookup"><span data-stu-id="8710b-111">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>  
  
    -   <span data-ttu-id="8710b-112">Если значение `i` меньше или равно 5, условие вычисляется как `true` и выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8710b-112">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="8710b-113">Оператор `Console.WriteLine` в теле цикла отображает значение `i`.</span><span class="sxs-lookup"><span data-stu-id="8710b-113">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="8710b-114">Значение `i` увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="8710b-114">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="8710b-115">Цикл возвращается к началу выполнения шага 2, чтобы повторно вычислить условие.</span><span class="sxs-lookup"><span data-stu-id="8710b-115">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="8710b-116">Если значение `i` больше 5, условие вычисляется как `false` и выполняется выход из цикла.</span><span class="sxs-lookup"><span data-stu-id="8710b-116">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
 <span data-ttu-id="8710b-117">Обратите внимание, что, если начальное значение `i` больше 5, тело цикла вообще не запускается.</span><span class="sxs-lookup"><span data-stu-id="8710b-117">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>  
  
 <span data-ttu-id="8710b-118">Каждый оператор `for` определяет инициализатор, условие и разделы итератора.</span><span class="sxs-lookup"><span data-stu-id="8710b-118">Every `for` statement defines initializer, condition, and iterator sections.</span></span> <span data-ttu-id="8710b-119">В этих разделах обычно задается количество итераций цикла.</span><span class="sxs-lookup"><span data-stu-id="8710b-119">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 <span data-ttu-id="8710b-120">Разделы служат для следующих целей.</span><span class="sxs-lookup"><span data-stu-id="8710b-120">The sections serve the following purposes.</span></span>  
  
-   <span data-ttu-id="8710b-121">Раздел инициализатора задает начальное условие.</span><span class="sxs-lookup"><span data-stu-id="8710b-121">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="8710b-122">Операторы в этом разделе выполняются только один раз, перед входом в цикл.</span><span class="sxs-lookup"><span data-stu-id="8710b-122">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="8710b-123">Раздел может содержать только один из двух параметров.</span><span class="sxs-lookup"><span data-stu-id="8710b-123">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="8710b-124">Объявление и инициализацию локальной переменной цикла (как в первом примере: `int i = 1`).</span><span class="sxs-lookup"><span data-stu-id="8710b-124">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="8710b-125">Переменная является локальной для цикла: к ней нельзя получить доступ из-за его пределов.</span><span class="sxs-lookup"><span data-stu-id="8710b-125">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="8710b-126">Нуль или более выражений операторов из следующего списка, разделенные запятыми:</span><span class="sxs-lookup"><span data-stu-id="8710b-126">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="8710b-127">оператор [присваивания](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8710b-127">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="8710b-128">вызов метода</span><span class="sxs-lookup"><span data-stu-id="8710b-128">invocation of a method</span></span>  
  
        -   <span data-ttu-id="8710b-129">префиксное или постфиксное выражение [приращения](../../../csharp/language-reference/operators/increment-operator.md), такое как `++i` или `i++`</span><span class="sxs-lookup"><span data-stu-id="8710b-129">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="8710b-130">префиксное или постфиксное выражение [декремента](../../../csharp/language-reference/operators/decrement-operator.md), такое как `--i` или `i--`</span><span class="sxs-lookup"><span data-stu-id="8710b-130">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="8710b-131">создание объекта с помощью оператора [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8710b-131">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="8710b-132">выражение [await](../../../csharp/language-reference/keywords/await.md)</span><span class="sxs-lookup"><span data-stu-id="8710b-132">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="8710b-133">В разделе условия содержится логическое выражение, которое вычисляется для определения необходимости выхода цикла или его повторного выполнения.</span><span class="sxs-lookup"><span data-stu-id="8710b-133">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="8710b-134">Раздел итератора определяет, что происходит после каждой итерации тела цикла.</span><span class="sxs-lookup"><span data-stu-id="8710b-134">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="8710b-135">Раздел итератора, содержащий ноль или более следующих выражений оператора, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="8710b-135">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="8710b-136">оператор [присваивания](../../../csharp/language-reference/operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8710b-136">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="8710b-137">вызов метода</span><span class="sxs-lookup"><span data-stu-id="8710b-137">invocation of a method</span></span>  
  
    -   <span data-ttu-id="8710b-138">префиксное или постфиксное выражение [приращения](../../../csharp/language-reference/operators/increment-operator.md), такое как `++i` или `i++`</span><span class="sxs-lookup"><span data-stu-id="8710b-138">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="8710b-139">префиксное или постфиксное выражение [декремента](../../../csharp/language-reference/operators/decrement-operator.md), такое как `--i` или `i--`</span><span class="sxs-lookup"><span data-stu-id="8710b-139">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="8710b-140">создание объекта с помощью оператора [new](../../../csharp/language-reference/keywords/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8710b-140">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="8710b-141">выражение [await](../../../csharp/language-reference/keywords/await.md)</span><span class="sxs-lookup"><span data-stu-id="8710b-141">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="8710b-142">Тело цикла состоит из оператора, пустого оператора или блока операторов, которые вы создаете, заключив ноль или более операторов в фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="8710b-142">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="8710b-143">Вы можете прервать цикл `for` с помощью ключевого слова [break](../../../csharp/language-reference/keywords/break.md) или перейти к следующей итерации с помощью ключевого слова [continue](../../../csharp/language-reference/keywords/continue.md).</span><span class="sxs-lookup"><span data-stu-id="8710b-143">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="8710b-144">Также можно выйти из любого цикла с помощью операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).</span><span class="sxs-lookup"><span data-stu-id="8710b-144">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
 <span data-ttu-id="8710b-145">В первом примере в этом разделе показан наиболее типичный тип цикла `for`, который выполняет следующие действия для разделов.</span><span class="sxs-lookup"><span data-stu-id="8710b-145">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections.</span></span>  
  
-   <span data-ttu-id="8710b-146">Инициализатор объявляет и инициализирует локальную переменную цикла `i`, которая хранит количество итераций цикла.</span><span class="sxs-lookup"><span data-stu-id="8710b-146">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="8710b-147">Условие проверяет значение переменной цикла, сравнивая его с известным окончательным значением 5.</span><span class="sxs-lookup"><span data-stu-id="8710b-147">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="8710b-148">Раздел итератора использует постфиксный оператор приращения, `i++`, для регистрации каждой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="8710b-148">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>  
  
 <span data-ttu-id="8710b-149">В следующем примере показаны несколько менее распространенные варианты: присваивание значения внешней переменной цикла в разделе инициализатора, вызов метода `Console.WriteLine` в разделах инициализатора и итератора и изменение значения двух переменных в разделе итератора.</span><span class="sxs-lookup"><span data-stu-id="8710b-149">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section,  invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 <span data-ttu-id="8710b-150">Все выражения, определяющие оператор `for`, являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="8710b-150">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="8710b-151">Например, следующая инструкция создает бесконечный цикл.</span><span class="sxs-lookup"><span data-stu-id="8710b-151">For example, the following statement creates an infinite loop.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8710b-152">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8710b-152">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8710b-153">См. также</span><span class="sxs-lookup"><span data-stu-id="8710b-153">See Also</span></span>  
 [<span data-ttu-id="8710b-154">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8710b-154">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8710b-155">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8710b-155">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8710b-156">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="8710b-156">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8710b-157">foreach, in</span><span class="sxs-lookup"><span data-stu-id="8710b-157">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="8710b-158">Оператор for (C++)</span><span class="sxs-lookup"><span data-stu-id="8710b-158">for Statement (C++)</span></span>](/cpp/cpp/for-statement-cpp)  
 [<span data-ttu-id="8710b-159">Операторы итерации</span><span class="sxs-lookup"><span data-stu-id="8710b-159">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
