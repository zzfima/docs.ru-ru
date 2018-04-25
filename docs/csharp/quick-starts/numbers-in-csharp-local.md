---
title: Руководство по числам в C#. Краткие руководства по локальной разработке на C#
description: Изучите C# на примере числовых типов, их свойств и методов.
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 6570693ea09ca2b548615291ba4f2b69f6d92482
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="numbers-in-c-quickstart"></a><span data-ttu-id="aced5-103">Краткое руководство по числам в C#</span><span class="sxs-lookup"><span data-stu-id="aced5-103">Numbers in C# quickstart</span></span>

<span data-ttu-id="aced5-104">Это краткое руководство поможет в интерактивном изучении числовых типов в C#.</span><span class="sxs-lookup"><span data-stu-id="aced5-104">This quickstart teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="aced5-105">Вы напишете небольшие фрагменты кода, затем скомпилируете и выполните этот код.</span><span class="sxs-lookup"><span data-stu-id="aced5-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="aced5-106">Это краткое руководство содержит ряд уроков, в которых рассматриваются числа и математические операции в C#.</span><span class="sxs-lookup"><span data-stu-id="aced5-106">The quickstart contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="aced5-107">В рамках этих занятий вы ознакомитесь с основами языка C#.</span><span class="sxs-lookup"><span data-stu-id="aced5-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="aced5-108">Для работы с этим кратким руководством вам потребуется компьютер, который можно использовать для разработки.</span><span class="sxs-lookup"><span data-stu-id="aced5-108">This quickstart expects you to have a machine you can use for development.</span></span> <span data-ttu-id="aced5-109">В руководстве по [началу работы с .NET за 10 минут](https://www.microsoft.com/net/core) содержатся инструкции по настройке локальной среды разработки на компьютерах Mac, Windows или Linux.</span><span class="sxs-lookup"><span data-stu-id="aced5-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="aced5-110">Краткий обзор команд, которые будут здесь использоваться, и ссылки на дополнительные сведения представлены в [вводной статье к руководствам по локальной разработке](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="aced5-110">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="aced5-111">Вычисления с целыми числами</span><span class="sxs-lookup"><span data-stu-id="aced5-111">Explore integer math</span></span>

<span data-ttu-id="aced5-112">Создайте каталог с именем **numbers-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="aced5-112">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="aced5-113">Откройте этот каталог и выполните команду `dotnet new console -n NumbersInCSharp -o .`.</span><span class="sxs-lookup"><span data-stu-id="aced5-113">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="aced5-114">Откройте файл **Program.cs** в любом редакторе и замените строку `Console.Writeline("Hello World!");` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="aced5-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="aced5-115">Чтобы выполнить этот код, введите `dotnet run` в окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="aced5-115">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="aced5-116">Вы увидели одну из основных математических операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="aced5-116">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="aced5-117">Тип `int` представляет **целое** положительное или отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="aced5-117">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="aced5-118">Для сложения используйте символ `+`.</span><span class="sxs-lookup"><span data-stu-id="aced5-118">You use the `+` symbol for addition.</span></span> <span data-ttu-id="aced5-119">Другие стандартные математические операции с целыми числами включают:</span><span class="sxs-lookup"><span data-stu-id="aced5-119">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="aced5-120">`-` — вычитание;</span><span class="sxs-lookup"><span data-stu-id="aced5-120">`-` for subtraction</span></span>
- <span data-ttu-id="aced5-121">`*` — умножение;</span><span class="sxs-lookup"><span data-stu-id="aced5-121">`*` for multiplication</span></span>
- <span data-ttu-id="aced5-122">`/` — деление.</span><span class="sxs-lookup"><span data-stu-id="aced5-122">`/` for division</span></span>

<span data-ttu-id="aced5-123">Начните с ознакомления с различными операциями.</span><span class="sxs-lookup"><span data-stu-id="aced5-123">Start by exploring those different operations.</span></span> <span data-ttu-id="aced5-124">Добавьте следующие строки после строки, с помощью которой записывается значение `c`:</span><span class="sxs-lookup"><span data-stu-id="aced5-124">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="aced5-125">Чтобы выполнить этот код, введите `dotnet run` в окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="aced5-125">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="aced5-126">Можно также поэкспериментировать, выполнив несколько математических операций в одной строке.</span><span class="sxs-lookup"><span data-stu-id="aced5-126">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="aced5-127">Например, выполните `c = a + b - 12 * 17;`.</span><span class="sxs-lookup"><span data-stu-id="aced5-127">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="aced5-128">Допускается сочетание переменных и постоянных чисел.</span><span class="sxs-lookup"><span data-stu-id="aced5-128">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="aced5-129">Вероятнее всего, при изучении C# (как и любого другого языка программирования) вы будете допускать ошибки в коде.</span><span class="sxs-lookup"><span data-stu-id="aced5-129">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="aced5-130">**Компилятор** найдет эти ошибки и сообщит вам о них.</span><span class="sxs-lookup"><span data-stu-id="aced5-130">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="aced5-131">Если результат содержит сообщения об ошибках, внимательно просмотрите пример кода и код в окне, чтобы понять, что нужно исправить.</span><span class="sxs-lookup"><span data-stu-id="aced5-131">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="aced5-132">Это упражнение поможет вам изучить структуру кода C#.</span><span class="sxs-lookup"><span data-stu-id="aced5-132">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="aced5-133">Вы завершили первый этап.</span><span class="sxs-lookup"><span data-stu-id="aced5-133">You've finished the first step.</span></span> <span data-ttu-id="aced5-134">Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="aced5-134">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="aced5-135">Это упростит начало работы с новым примером.</span><span class="sxs-lookup"><span data-stu-id="aced5-135">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="aced5-136">Переименуйте метод `Main` в `WorkingWithIntegers` и запишите новый метод `Main`, который вызывает `WorkingWithIntegers`.</span><span class="sxs-lookup"><span data-stu-id="aced5-136">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="aced5-137">В результате ваш код должен выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aced5-137">When you have finished, your code should look like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a><span data-ttu-id="aced5-138">Изучение порядка операций</span><span class="sxs-lookup"><span data-stu-id="aced5-138">Explore order of operations</span></span>

<span data-ttu-id="aced5-139">Закомментируйте вызов `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="aced5-139">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="aced5-140">Это поможет упорядочить выходные данные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="aced5-140">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="aced5-141">`//` запускает **комментарий** в C#.</span><span class="sxs-lookup"><span data-stu-id="aced5-141">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="aced5-142">Комментарии — это любой текст, который должен быть сохранен в исходном коде, но не должен выполняться как код.</span><span class="sxs-lookup"><span data-stu-id="aced5-142">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="aced5-143">Компилятор не создает исполняемый код из комментариев.</span><span class="sxs-lookup"><span data-stu-id="aced5-143">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="aced5-144">Язык C# определяет приоритет математических операций в соответствии с правилами математики.</span><span class="sxs-lookup"><span data-stu-id="aced5-144">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="aced5-145">Умножение и деление имеют приоритет над сложением и вычитанием.</span><span class="sxs-lookup"><span data-stu-id="aced5-145">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="aced5-146">Убедитесь в этом, добавив следующий код в метод `Main` и выполнив команду `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="aced5-146">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="aced5-147">В выходных данных видно, что умножение выполняется раньше сложения.</span><span class="sxs-lookup"><span data-stu-id="aced5-147">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="aced5-148">Можно применить другую последовательность операций. Для этого операции, которые должны выполняться первыми, нужно заключить в скобки.</span><span class="sxs-lookup"><span data-stu-id="aced5-148">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="aced5-149">Добавьте приведенные ниже строки и выполните код еще раз.</span><span class="sxs-lookup"><span data-stu-id="aced5-149">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="aced5-150">Поэкспериментируйте, объединяя различные операции.</span><span class="sxs-lookup"><span data-stu-id="aced5-150">Explore more by combining many different operations.</span></span> <span data-ttu-id="aced5-151">Добавьте в конец метода `Main` строки, подобные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="aced5-151">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="aced5-152">Выполните `dotnet run` еще раз.</span><span class="sxs-lookup"><span data-stu-id="aced5-152">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="aced5-153">Возможно, вы заметили интересное поведение целых чисел.</span><span class="sxs-lookup"><span data-stu-id="aced5-153">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="aced5-154">Деление целых чисел всегда дает результат в виде целого числа, даже если ожидаемый результат содержит десятичную или дробную часть.</span><span class="sxs-lookup"><span data-stu-id="aced5-154">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="aced5-155">Если вы еще не видели пример такого поведения, добавьте следующий код в конец метода `Main`:</span><span class="sxs-lookup"><span data-stu-id="aced5-155">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="aced5-156">Выполните `dotnet run` еще раз, чтобы просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="aced5-156">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="aced5-157">Прежде чем продолжить, давайте поместив весь код, который вы написали в этом разделе, в новый метод.</span><span class="sxs-lookup"><span data-stu-id="aced5-157">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="aced5-158">Вызовите этот новый метод `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="aced5-158">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="aced5-159">Результат должен выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="aced5-159">You should end up with something like this:</span></span>

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {   
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a  + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="aced5-160">Изучение точности и ограничений для целых чисел</span><span class="sxs-lookup"><span data-stu-id="aced5-160">Explore integer precision and limits</span></span>
<span data-ttu-id="aced5-161">В последнем примере вы увидели, что при делении целых чисел результат усекается.</span><span class="sxs-lookup"><span data-stu-id="aced5-161">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="aced5-162">Вы можете получить **остаток** с помощью оператора **остатка от деления**, который обозначается символом `%`.</span><span class="sxs-lookup"><span data-stu-id="aced5-162">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="aced5-163">Попробуйте добавить приведенный ниже код в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="aced5-163">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="aced5-164">Тип целых чисел C# характеризуется еще одним отличием от математических целых: тип `int` имеет минимальные и максимальные ограничения.</span><span class="sxs-lookup"><span data-stu-id="aced5-164">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="aced5-165">Добавьте следующий код в метод `Main`, чтобы просмотреть эти ограничения:</span><span class="sxs-lookup"><span data-stu-id="aced5-165">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="aced5-166">Если при вычислении выводится значение вне этих пределов, возникает условие **потери значимости** или **переполнения**.</span><span class="sxs-lookup"><span data-stu-id="aced5-166">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="aced5-167">Ответ должен находиться в диапазоне от минимального до максимального значения.</span><span class="sxs-lookup"><span data-stu-id="aced5-167">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="aced5-168">Добавьте следующие две строки в метод `Main`, чтобы увидеть пример:</span><span class="sxs-lookup"><span data-stu-id="aced5-168">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="aced5-169">Обратите внимание, что ответ очень близок к минимальному целому числу (отрицательное значение).</span><span class="sxs-lookup"><span data-stu-id="aced5-169">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="aced5-170">Он совпадает со значением `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="aced5-170">It's the same as `min + 2`.</span></span> <span data-ttu-id="aced5-171">Оператор сложения **вызвал переполнение** допустимых значений для целых чисел.</span><span class="sxs-lookup"><span data-stu-id="aced5-171">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="aced5-172">Ответ является очень большим отрицательным числом, так как переполнение покрывает диапазон от наибольшего целого числа до наименьшего.</span><span class="sxs-lookup"><span data-stu-id="aced5-172">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="aced5-173">Существуют другие числовые типы с различными ограничениями и точностью, которые можно использовать, если тип `int` не соответствует вашим требованиям.</span><span class="sxs-lookup"><span data-stu-id="aced5-173">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="aced5-174">Рассмотрим их.</span><span class="sxs-lookup"><span data-stu-id="aced5-174">Let's explore those next.</span></span>

<span data-ttu-id="aced5-175">Давайте еще раз переместим код, написанный в этом разделе, в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="aced5-175">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="aced5-176">Присвойте обработчику события имя `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="aced5-176">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="aced5-177">Работа с типом double</span><span class="sxs-lookup"><span data-stu-id="aced5-177">Work with the double type</span></span>

<span data-ttu-id="aced5-178">Числовой тип `double` представляет число с плавающей запятой двойной точности.</span><span class="sxs-lookup"><span data-stu-id="aced5-178">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="aced5-179">Эти термины могут быть новыми для вас.</span><span class="sxs-lookup"><span data-stu-id="aced5-179">Those terms may be new to you.</span></span> <span data-ttu-id="aced5-180">Число **с плавающей запятой** можно использовать для представления нецелых чисел, которые могут быть очень большими или малыми.</span><span class="sxs-lookup"><span data-stu-id="aced5-180">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="aced5-181">**Двойная точность** означает, что для хранения этих чисел используется большая точность, чем **одиночная**.</span><span class="sxs-lookup"><span data-stu-id="aced5-181">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="aced5-182">На современных компьютерах числа с двойной точностью используется чаще, чем с одиночной.</span><span class="sxs-lookup"><span data-stu-id="aced5-182">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="aced5-183">Рассмотрим их.</span><span class="sxs-lookup"><span data-stu-id="aced5-183">Let's explore.</span></span> <span data-ttu-id="aced5-184">Добавьте следующий код и просмотрите результат:</span><span class="sxs-lookup"><span data-stu-id="aced5-184">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="aced5-185">Обратите внимание, что ответ включает десятичную долю частного.</span><span class="sxs-lookup"><span data-stu-id="aced5-185">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="aced5-186">Попробуйте более сложное выражение с типом double:</span><span class="sxs-lookup"><span data-stu-id="aced5-186">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="aced5-187">Диапазон значений типа double гораздо больше, чем диапазон значений целых чисел.</span><span class="sxs-lookup"><span data-stu-id="aced5-187">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="aced5-188">Добавьте следующий фрагмент после написанного кода:</span><span class="sxs-lookup"><span data-stu-id="aced5-188">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="aced5-189">Значения выводятся в экспоненциальном представлении.</span><span class="sxs-lookup"><span data-stu-id="aced5-189">These values are printed out in scientific notation.</span></span> <span data-ttu-id="aced5-190">Число слева от символа `E` является значащим.</span><span class="sxs-lookup"><span data-stu-id="aced5-190">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="aced5-191">Число справа — это показатель степени, который равен 10.</span><span class="sxs-lookup"><span data-stu-id="aced5-191">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="aced5-192">Так же, как десятичные числа в математике, значения double в C# могут содержать ошибки округления.</span><span class="sxs-lookup"><span data-stu-id="aced5-192">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="aced5-193">Выполните этот код:</span><span class="sxs-lookup"><span data-stu-id="aced5-193">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="aced5-194">Вы знаете, что периодическая десятичная дробь `0.3` не равняется `1/3`.</span><span class="sxs-lookup"><span data-stu-id="aced5-194">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="aced5-195">***Задача***</span><span class="sxs-lookup"><span data-stu-id="aced5-195">***Challenge***</span></span>

<span data-ttu-id="aced5-196">Выполните другие вычисления с большими числами, малыми числами, умножением и делением с помощью типа `double`.</span><span class="sxs-lookup"><span data-stu-id="aced5-196">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="aced5-197">Попробуйте выполнить более сложные вычисления.</span><span class="sxs-lookup"><span data-stu-id="aced5-197">Try more complicated calculations.</span></span>

<span data-ttu-id="aced5-198">После того как вы решите сложную задачу, поместите написанный код в новый метод.</span><span class="sxs-lookup"><span data-stu-id="aced5-198">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="aced5-199">Присвойте этому методу имя `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="aced5-199">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="aced5-200">Работа с типами с фиксированной запятой</span><span class="sxs-lookup"><span data-stu-id="aced5-200">Work with fixed point types</span></span>

<span data-ttu-id="aced5-201">Вы уже ознакомились с базовыми числовыми типами в C# — целыми числами и числами типа double.</span><span class="sxs-lookup"><span data-stu-id="aced5-201">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="aced5-202">Осталось изучить еще один тип: `decimal`.</span><span class="sxs-lookup"><span data-stu-id="aced5-202">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="aced5-203">Тип `decimal` имеет меньший диапазон, но большую точность, чем `double`.</span><span class="sxs-lookup"><span data-stu-id="aced5-203">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="aced5-204">Термин **фиксированная запятая** означает, что десятичный (или двоичный) разделитель не перемещается.</span><span class="sxs-lookup"><span data-stu-id="aced5-204">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="aced5-205">Например:</span><span class="sxs-lookup"><span data-stu-id="aced5-205">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="aced5-206">Обратите внимание, что диапазон меньше, чем для типа `double`.</span><span class="sxs-lookup"><span data-stu-id="aced5-206">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="aced5-207">Вы можете убедиться в повышении точности при использовании типа decimal, выполнив следующий код:</span><span class="sxs-lookup"><span data-stu-id="aced5-207">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="aced5-208">Суффикс `M` возле чисел указывает, что для константы должен использоваться тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="aced5-208">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="aced5-209">Обратите внимание, что при вычислении с использованием типа decimal справа от запятой содержится больше цифр.</span><span class="sxs-lookup"><span data-stu-id="aced5-209">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="aced5-210">***Задача***</span><span class="sxs-lookup"><span data-stu-id="aced5-210">***Challenge***</span></span>

<span data-ttu-id="aced5-211">Теперь, когда вы ознакомились с разными числовыми типами, напишите код, который позволяет вычислить площадь круга с радиусом 2,50 см.</span><span class="sxs-lookup"><span data-stu-id="aced5-211">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 centimeters.</span></span> <span data-ttu-id="aced5-212">Помните, что площадь круга равна квадрату радиуса, умноженному на число пи.</span><span class="sxs-lookup"><span data-stu-id="aced5-212">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="aced5-213">Подсказка: в .NET есть константа пи <xref:System.Math.PI?displayProperty=nameWithType>, которую можно использовать.</span><span class="sxs-lookup"><span data-stu-id="aced5-213">One hint: .NET contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="aced5-214">Вы должны получить ответ от 19 до 20.</span><span class="sxs-lookup"><span data-stu-id="aced5-214">You should get an answer between 19 and 20.</span></span>
<span data-ttu-id="aced5-215">Ответ можно [просмотреть в готовом примере кода в GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).</span><span class="sxs-lookup"><span data-stu-id="aced5-215">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="aced5-216">При желании поэкспериментируйте с другими формулами.</span><span class="sxs-lookup"><span data-stu-id="aced5-216">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="aced5-217">Вы выполнили все задачи краткого руководства по числам в C#.</span><span class="sxs-lookup"><span data-stu-id="aced5-217">You've completed the "Numbers in C#" quickstart.</span></span> <span data-ttu-id="aced5-218">Теперь вы можете выполнить руководство по [ветвям и циклам](branches-and-loops-local.md) в своей среде разработки.</span><span class="sxs-lookup"><span data-stu-id="aced5-218">You can continue with the [Branches and loops](branches-and-loops-local.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="aced5-219">Дополнительные сведения о числах в C# см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="aced5-219">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="aced5-220">[Таблица целых типов](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="aced5-220">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="aced5-221">[Таблица типов с плавающей запятой](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="aced5-221">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="aced5-222">[Таблица встроенных типов](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="aced5-222">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="aced5-223">[Таблица неявных числовых преобразований](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="aced5-223">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="aced5-224">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="aced5-224">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)

