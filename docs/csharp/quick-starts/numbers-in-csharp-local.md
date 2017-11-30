---
title: "Краткое руководство - чисел в C# - руководство по C#"
description: "Изучение C#, изучив числовые типы, их свойства и методы."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 821cca4ea6d6148410e9b179f05d5b74c4844628
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2017
---
# <a name="numbers-in-c-quick-start"></a><span data-ttu-id="024cb-103">Числа в C# быстрого запуска</span><span class="sxs-lookup"><span data-stu-id="024cb-103">Numbers in C# quick start</span></span> #

<span data-ttu-id="024cb-104">Это краткое руководство содержит сведения о числовых типов в C# интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="024cb-104">This quick start teaches you about the number types in C# interactively.</span></span> <span data-ttu-id="024cb-105">Вы будете писать небольшие фрагменты кода, а затем будет компиляция и выполнение этого кода.</span><span class="sxs-lookup"><span data-stu-id="024cb-105">You'll write small amounts of code, then you'll compile and run that code.</span></span> <span data-ttu-id="024cb-106">Краткое руководство содержит ряд занятий для просмотра номера и математические операции в C#.</span><span class="sxs-lookup"><span data-stu-id="024cb-106">The quick start contains a series of lessons that explore numbers and math operations in C#.</span></span> <span data-ttu-id="024cb-107">В рамках этих занятий вы ознакомитесь с основами языка C#.</span><span class="sxs-lookup"><span data-stu-id="024cb-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="024cb-108">В этом кратком руководстве предполагается, что вы машины, которые можно использовать для разработки приложений.</span><span class="sxs-lookup"><span data-stu-id="024cb-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="024cb-109">В разделе .NET [приступить к работе в течение 10 минут](https://www.microsoft.com/net/core) содержит инструкции по настройке в локальной среде разработки на Mac, ПК или Linux.</span><span class="sxs-lookup"><span data-stu-id="024cb-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="explore-integer-math"></a><span data-ttu-id="024cb-110">Вычисления с целыми числами</span><span class="sxs-lookup"><span data-stu-id="024cb-110">Explore integer math</span></span>

<span data-ttu-id="024cb-111">Создайте каталог с именем **краткое руководство номера**.</span><span class="sxs-lookup"><span data-stu-id="024cb-111">Create a directory named **numbers-quickstart**.</span></span> <span data-ttu-id="024cb-112">Откройте этот каталог и выполните команду `dotnet new console -n NumbersInCSharp -o .`.</span><span class="sxs-lookup"><span data-stu-id="024cb-112">Make that the current directory and run `dotnet new console -n NumbersInCSharp -o .`.</span></span>

<span data-ttu-id="024cb-113">Откройте **Program.cs** в любом редакторе и замените строку `Console.Writeline("Hello World!");` со следующим:</span><span class="sxs-lookup"><span data-stu-id="024cb-113">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following:</span></span>

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

<span data-ttu-id="024cb-114">Выполните этот код, введя `dotnet run` в окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="024cb-114">Run this code by typing `dotnet run` in your command window.</span></span> 

<span data-ttu-id="024cb-115">Вы увидели одну из основных математических операций с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="024cb-115">You've just seen one of the fundamental math operations with integers.</span></span> <span data-ttu-id="024cb-116">Тип `int` представляет **целое** положительное или отрицательное число.</span><span class="sxs-lookup"><span data-stu-id="024cb-116">The `int` type represents an **integer**, a positive or negative whole number.</span></span> <span data-ttu-id="024cb-117">Для сложения используйте символ `+`.</span><span class="sxs-lookup"><span data-stu-id="024cb-117">You use the `+` symbol for addition.</span></span> <span data-ttu-id="024cb-118">Другие стандартные математические операции с целыми числами включают:</span><span class="sxs-lookup"><span data-stu-id="024cb-118">Other common mathematical operations for integers include:</span></span>

- <span data-ttu-id="024cb-119">`-` — вычитание;</span><span class="sxs-lookup"><span data-stu-id="024cb-119">`-` for subtraction</span></span>
- <span data-ttu-id="024cb-120">`*` — умножение;</span><span class="sxs-lookup"><span data-stu-id="024cb-120">`*` for multiplication</span></span>
- <span data-ttu-id="024cb-121">`/` — деление.</span><span class="sxs-lookup"><span data-stu-id="024cb-121">`/` for division</span></span>

<span data-ttu-id="024cb-122">Начните с ознакомления с различными операциями.</span><span class="sxs-lookup"><span data-stu-id="024cb-122">Start by exploring those different operations.</span></span> <span data-ttu-id="024cb-123">Добавьте следующие строки после строки, которая записывает значение `c`:</span><span class="sxs-lookup"><span data-stu-id="024cb-123">Add these lines after the line that writes the value of `c`:</span></span>

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

<span data-ttu-id="024cb-124">Выполните этот код, введя `dotnet run` в окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="024cb-124">Run this code by typing `dotnet run` in your command window.</span></span> 
    
<span data-ttu-id="024cb-125">Можно также поэкспериментировать, выполнив несколько математических операций в одной строке.</span><span class="sxs-lookup"><span data-stu-id="024cb-125">You can also experiment by performing multiple mathematics operations in the same line, if you'd like.</span></span> <span data-ttu-id="024cb-126">Повторите `c = a + b - 12 * 17;` например.</span><span class="sxs-lookup"><span data-stu-id="024cb-126">Try `c = a + b - 12 * 17;` for example.</span></span> <span data-ttu-id="024cb-127">Допускается сочетание переменных и констант чисел.</span><span class="sxs-lookup"><span data-stu-id="024cb-127">Mixing variables and constant numbers is allowed.</span></span>

> [!TIP]
> <span data-ttu-id="024cb-128">Вероятнее всего, при изучении C# (как и любого другого языка программирования) вы будете допускать ошибки в коде.</span><span class="sxs-lookup"><span data-stu-id="024cb-128">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="024cb-129">**Компилятор** найдет эти ошибки и сообщит вам о них.</span><span class="sxs-lookup"><span data-stu-id="024cb-129">The **compiler** will find those errors and report them to you.</span></span> <span data-ttu-id="024cb-130">Если результат содержит сообщения об ошибках, внимательно посмотрите на код примера и код в окне таким образом, чтобы увидеть, что следует исправить.</span><span class="sxs-lookup"><span data-stu-id="024cb-130">When the output contains error messages, look closely at the example code and the code in your window to see what to fix.</span></span>
> <span data-ttu-id="024cb-131">Это упражнение поможет вам изучить структуру кода C#.</span><span class="sxs-lookup"><span data-stu-id="024cb-131">That exercise will help you learn the structure of C# code.</span></span>     

<span data-ttu-id="024cb-132">После завершения первого шага.</span><span class="sxs-lookup"><span data-stu-id="024cb-132">You've finished the first step.</span></span> <span data-ttu-id="024cb-133">Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="024cb-133">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="024cb-134">Это упростит начало работы с новым примером.</span><span class="sxs-lookup"><span data-stu-id="024cb-134">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="024cb-135">Переименуйте метод `Main` в `WorkingWithIntegers` и запишите новый метод `Main`, который вызывает `WorkingWithIntegers`.</span><span class="sxs-lookup"><span data-stu-id="024cb-135">Rename your `Main` method to `WorkingWithIntegers` and write a new `Main` method that calls `WorkingWithIntegers`.</span></span> <span data-ttu-id="024cb-136">В результате ваш код должен выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="024cb-136">When you have finished, your code should look like this:</span></span>

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

## <a name="explore-order-of-operations"></a><span data-ttu-id="024cb-137">Изучение порядка операций</span><span class="sxs-lookup"><span data-stu-id="024cb-137">Explore order of operations</span></span>

<span data-ttu-id="024cb-138">Закомментируйте вызов `WorkingWithIntegers()`.</span><span class="sxs-lookup"><span data-stu-id="024cb-138">Comment out the call to `WorkingWithIntegers()`.</span></span> <span data-ttu-id="024cb-139">Это сделает менее перегружена, при работе в этом разделе выходные данные:</span><span class="sxs-lookup"><span data-stu-id="024cb-139">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//WorkingWithIntegers();
```

<span data-ttu-id="024cb-140">`//` Запускает **комментарий** в C#.</span><span class="sxs-lookup"><span data-stu-id="024cb-140">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="024cb-141">Комментарии — это текст, который требуется сохранить в исходном коде, но не выполнять как код.</span><span class="sxs-lookup"><span data-stu-id="024cb-141">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="024cb-142">Компилятор не создает исполняемого кода из комментариев.</span><span class="sxs-lookup"><span data-stu-id="024cb-142">The compiler does not generate any executable code from comments.</span></span>

<span data-ttu-id="024cb-143">Язык C# определяет приоритет математических операций в соответствии с правилами математики.</span><span class="sxs-lookup"><span data-stu-id="024cb-143">The C# language defines the precedence of different mathematics operations with rules consistent with the rules you learned in mathematics.</span></span>
<span data-ttu-id="024cb-144">Умножение и деление имеют приоритет над сложением и вычитанием.</span><span class="sxs-lookup"><span data-stu-id="024cb-144">Multiplication and division take precedence over addition and subtraction.</span></span>
<span data-ttu-id="024cb-145">Просмотр, добавив следующий код, чтобы ваш `Main` метод и execuing `dotnet run`:</span><span class="sxs-lookup"><span data-stu-id="024cb-145">Explore that by adding the following code to your `Main` method, and execuing `dotnet run`:</span></span>

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

<span data-ttu-id="024cb-146">В выходных данных видно, что умножение выполняется раньше сложения.</span><span class="sxs-lookup"><span data-stu-id="024cb-146">The output demonstrates that the multiplication is performed before the addition.</span></span>

<span data-ttu-id="024cb-147">Можно принудительно последовательности, отличной от операции, добавляя скобки вокруг операции или операций, которые должны выполняются первыми.</span><span class="sxs-lookup"><span data-stu-id="024cb-147">You can force a different order of operation by adding parentheses around the operation or operations you want performed first.</span></span> <span data-ttu-id="024cb-148">Добавьте следующие строки и снова запустите:</span><span class="sxs-lookup"><span data-stu-id="024cb-148">Add the following lines and run again:</span></span>

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

<span data-ttu-id="024cb-149">Поэкспериментируйте, объединяя различные операции.</span><span class="sxs-lookup"><span data-stu-id="024cb-149">Explore more by combining many different operations.</span></span> <span data-ttu-id="024cb-150">Добавить примерно следующие строки в нижней части вашего `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="024cb-150">Add something like the following lines at the bottom of your `Main` method.</span></span> <span data-ttu-id="024cb-151">Повторите `dotnet run` еще раз.</span><span class="sxs-lookup"><span data-stu-id="024cb-151">Try `dotnet run` again.</span></span>

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

<span data-ttu-id="024cb-152">Возможно, вы заметили интересное поведение целых чисел.</span><span class="sxs-lookup"><span data-stu-id="024cb-152">You may have noticed an interesting behavior for integers.</span></span> <span data-ttu-id="024cb-153">Целочисленное деление всегда создает целочисленный результат, даже в том случае, если ожидается результатов включать десятичный или дробной части.</span><span class="sxs-lookup"><span data-stu-id="024cb-153">Integer division always produces an integer result, even when you'd expect the result to include a decimal or fractional portion.</span></span>

<span data-ttu-id="024cb-154">Если такое поведение не видели, выполните следующий код в конце вашей `Main` метод:</span><span class="sxs-lookup"><span data-stu-id="024cb-154">If you haven't seen this behavior, try the following code at the end of your `Main` method:</span></span>

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="024cb-155">Тип `dotnet run` еще раз, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="024cb-155">Type `dotnet run` again to see the results.</span></span>

<span data-ttu-id="024cb-156">Прежде чем продолжить, давайте кода записаны в этом разделе и поместить его в новый метод.</span><span class="sxs-lookup"><span data-stu-id="024cb-156">Before moving on, let's take all the code you've written in this section and put it in a new method.</span></span> <span data-ttu-id="024cb-157">Вызывайте этот новый метод `OrderPrecedence`.</span><span class="sxs-lookup"><span data-stu-id="024cb-157">Call that new method `OrderPrecedence`.</span></span>
<span data-ttu-id="024cb-158">Вы должен получиться примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="024cb-158">You should end up with something like this:</span></span>

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

## <a name="explore-integer-precision-and-limits"></a><span data-ttu-id="024cb-159">Изучение точности и ограничений для целых чисел</span><span class="sxs-lookup"><span data-stu-id="024cb-159">Explore integer precision and limits</span></span>
<span data-ttu-id="024cb-160">В последнем примере вы увидели, что при делении целых чисел результат усекается.</span><span class="sxs-lookup"><span data-stu-id="024cb-160">That last sample showed you that integer division truncates the result.</span></span>
<span data-ttu-id="024cb-161">Вы можете получить **остаток** с помощью **остаток от деления** оператор, `%` символ.</span><span class="sxs-lookup"><span data-stu-id="024cb-161">You can get the **remainder** by using the **modulo** operator, the `%` character.</span></span> <span data-ttu-id="024cb-162">Выполните следующий код в вашей `Main` метод:</span><span class="sxs-lookup"><span data-stu-id="024cb-162">Try the following code in your `Main` method:</span></span>

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

<span data-ttu-id="024cb-163">Тип целых чисел C# характеризуется еще одним отличием от математических целых: тип `int` имеет минимальные и максимальные ограничения.</span><span class="sxs-lookup"><span data-stu-id="024cb-163">The C# integer type differs from mathematical integers in one other way: the `int` type has minimum and maximum limits.</span></span> <span data-ttu-id="024cb-164">Добавьте следующий код в вашей `Main` метод для просмотра этих ограничений:</span><span class="sxs-lookup"><span data-stu-id="024cb-164">Add this code to your `Main` method to see those limits:</span></span>
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

<span data-ttu-id="024cb-165">Если при вычислении выводится значение вне этих пределов, возникает условие **потери значимости** или **переполнения**.</span><span class="sxs-lookup"><span data-stu-id="024cb-165">If a calculation produces a value that exceeds those limits, you have an **underflow** or **overflow** condition.</span></span> <span data-ttu-id="024cb-166">Ответ должен находиться в диапазоне от минимального до максимального значения.</span><span class="sxs-lookup"><span data-stu-id="024cb-166">The answer appears to wrap from one limit to the other.</span></span> <span data-ttu-id="024cb-167">Добавьте следующие две строки в вашей `Main` метод в качестве примера:</span><span class="sxs-lookup"><span data-stu-id="024cb-167">Add these two lines to your `Main` method to see an example:</span></span>

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
<span data-ttu-id="024cb-168">Обратите внимание, что ответ очень близок к минимальному целому числу (отрицательное значение).</span><span class="sxs-lookup"><span data-stu-id="024cb-168">Notice that the answer is very close to the minimum (negative) integer.</span></span> <span data-ttu-id="024cb-169">Он совпадает со значением `min + 2`.</span><span class="sxs-lookup"><span data-stu-id="024cb-169">It's the same as `min + 2`.</span></span> <span data-ttu-id="024cb-170">Оператор сложения **вызвал переполнение** допустимых значений для целых чисел.</span><span class="sxs-lookup"><span data-stu-id="024cb-170">The addition operation **overflowed** the allowed values for integers.</span></span>
<span data-ttu-id="024cb-171">Ответ является очень большим отрицательным числом, так как переполнение покрывает диапазон от наибольшего целого числа до наименьшего.</span><span class="sxs-lookup"><span data-stu-id="024cb-171">The answer is a very large negative number because an overflow "wraps around" from the largest possible integer value to the smallest.</span></span>

<span data-ttu-id="024cb-172">Существуют другие числовые типы с различными ограничениями и точностью, которые можно использовать, если тип `int` не соответствует вашим требованиям.</span><span class="sxs-lookup"><span data-stu-id="024cb-172">There are other numeric types with different limits and precision that you would use when the `int` type doesn't meet your needs.</span></span> <span data-ttu-id="024cb-173">Рассмотрим их.</span><span class="sxs-lookup"><span data-stu-id="024cb-173">Let's explore those next.</span></span>

<span data-ttu-id="024cb-174">Опять же давайте переместите код, записанный в этом разделе в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="024cb-174">Once again, let's move the code you wrote in this section into a separate method.</span></span> <span data-ttu-id="024cb-175">Присвойте обработчику события имя `TestLimits`.</span><span class="sxs-lookup"><span data-stu-id="024cb-175">Name it `TestLimits`.</span></span> 

## <a name="work-with-the-double-type"></a><span data-ttu-id="024cb-176">Работа с типом double</span><span class="sxs-lookup"><span data-stu-id="024cb-176">Work with the double type</span></span>

<span data-ttu-id="024cb-177">Числовой тип `double` представляет число с плавающей запятой двойной точности.</span><span class="sxs-lookup"><span data-stu-id="024cb-177">The `double` numeric type represents a double-precision floating point number.</span></span> <span data-ttu-id="024cb-178">Эти термины могут быть новыми для вас.</span><span class="sxs-lookup"><span data-stu-id="024cb-178">Those terms may be new to you.</span></span> <span data-ttu-id="024cb-179">Объект **число с плавающей запятой** номер полезен для представления чисел не интегрированные, может быть очень большие или малые по величине.</span><span class="sxs-lookup"><span data-stu-id="024cb-179">A **floating point** number is useful to represent non-integral numbers that may be very large or small in magnitude.</span></span> <span data-ttu-id="024cb-180">**Двойная точность** означает, что для хранения этих чисел используется большая точность, чем **одиночная**.</span><span class="sxs-lookup"><span data-stu-id="024cb-180">**Double-precision** means that these numbers are stored using greater precision than **single-precision**.</span></span> <span data-ttu-id="024cb-181">На современных компьютерах числа с двойной точностью используется чаще, чем с одиночной.</span><span class="sxs-lookup"><span data-stu-id="024cb-181">On modern computers, it is more common to use double precision than single precision numbers.</span></span>
<span data-ttu-id="024cb-182">Рассмотрим их.</span><span class="sxs-lookup"><span data-stu-id="024cb-182">Let's explore.</span></span> <span data-ttu-id="024cb-183">Добавьте следующий код и просмотреть результат:</span><span class="sxs-lookup"><span data-stu-id="024cb-183">Add the following code and see the result:</span></span>

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

<span data-ttu-id="024cb-184">Обратите внимание, что ответ включает десятичную долю частного.</span><span class="sxs-lookup"><span data-stu-id="024cb-184">Notice that the answer includes the decimal portion of the quotient.</span></span> <span data-ttu-id="024cb-185">Попробуйте более сложное выражение с типом double:</span><span class="sxs-lookup"><span data-stu-id="024cb-185">Try a slightly more complicated expression with doubles:</span></span>

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

<span data-ttu-id="024cb-186">Диапазон значений типа double гораздо больше, чем диапазон значений целых чисел.</span><span class="sxs-lookup"><span data-stu-id="024cb-186">The range of a double value is much greater than integer values.</span></span> <span data-ttu-id="024cb-187">Попробуйте выполните следующий код под ваши записи к текущему моменту.</span><span class="sxs-lookup"><span data-stu-id="024cb-187">Try the following code below what you've written so far:</span></span>

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

<span data-ttu-id="024cb-188">Эти значения выводятся в экспоненциальном представлении.</span><span class="sxs-lookup"><span data-stu-id="024cb-188">These values are printed out in scientific notation.</span></span> <span data-ttu-id="024cb-189">Число слева от `E` является значащей части числа.</span><span class="sxs-lookup"><span data-stu-id="024cb-189">The number to the left of the `E` is the significand.</span></span> <span data-ttu-id="024cb-190">Число справа — это показатель степени, который равен 10.</span><span class="sxs-lookup"><span data-stu-id="024cb-190">The number to the right is the exponent, as a power of 10.</span></span> 

<span data-ttu-id="024cb-191">Так же, как десятичные числа в математике, значения double в C# могут содержать ошибки округления.</span><span class="sxs-lookup"><span data-stu-id="024cb-191">Just like decimal numbers in math, doubles in C# can have rounding errors.</span></span> <span data-ttu-id="024cb-192">Выполните этот код:</span><span class="sxs-lookup"><span data-stu-id="024cb-192">Try this code:</span></span>

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

<span data-ttu-id="024cb-193">Вы знаете, что периодическая десятичная дробь `0.3` не равняется `1/3`.</span><span class="sxs-lookup"><span data-stu-id="024cb-193">You know that `0.3` repeating is not exactly the same as `1/3`.</span></span>

<span data-ttu-id="024cb-194">***Задача***</span><span class="sxs-lookup"><span data-stu-id="024cb-194">***Challenge***</span></span>

<span data-ttu-id="024cb-195">Выполните другие вычисления с большими числами, малыми числами, умножением и делением с помощью типа `double`.</span><span class="sxs-lookup"><span data-stu-id="024cb-195">Try other calculations with large numbers, small numbers, multiplication and division using the `double` type.</span></span>  <span data-ttu-id="024cb-196">Попробуйте выполнить более сложные вычисления.</span><span class="sxs-lookup"><span data-stu-id="024cb-196">Try more complicated calculations.</span></span>

<span data-ttu-id="024cb-197">После потратили время с проблемой, выполнить код, написанный и поместите его в новый метод.</span><span class="sxs-lookup"><span data-stu-id="024cb-197">After you've spent some time with the challenge, take the code you've written and place it in a new method.</span></span> <span data-ttu-id="024cb-198">Назовите этот новый метод `WorkWithDoubles`.</span><span class="sxs-lookup"><span data-stu-id="024cb-198">Name that new method `WorkWithDoubles`.</span></span>

## <a name="work-with-fixed-point-types"></a><span data-ttu-id="024cb-199">Работа с типами с фиксированной запятой</span><span class="sxs-lookup"><span data-stu-id="024cb-199">Work with fixed point types</span></span>

<span data-ttu-id="024cb-200">Вы уже ознакомились с базовыми числовыми типами в C# — целыми числами и числами типа double.</span><span class="sxs-lookup"><span data-stu-id="024cb-200">You've seen the basic numeric types in C#: integers and doubles.</span></span>  <span data-ttu-id="024cb-201">Осталось изучить еще один тип: `decimal`.</span><span class="sxs-lookup"><span data-stu-id="024cb-201">There is one other type to learn: the `decimal` type.</span></span> <span data-ttu-id="024cb-202">`decimal` Тип имеет меньший диапазон, но большую точность, чем `double`.</span><span class="sxs-lookup"><span data-stu-id="024cb-202">The `decimal` type has a smaller range but greater precision than `double`.</span></span> <span data-ttu-id="024cb-203">Термин **фиксированная запятая** означает, что десятичный (или двоичный) разделитель не перемещается.</span><span class="sxs-lookup"><span data-stu-id="024cb-203">The term **fixed point** means that the decimal point (or binary point) doesn't move.</span></span> <span data-ttu-id="024cb-204">Например:</span><span class="sxs-lookup"><span data-stu-id="024cb-204">Let's take a look:</span></span>

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

<span data-ttu-id="024cb-205">Обратите внимание, что диапазон меньше, чем для типа `double`.</span><span class="sxs-lookup"><span data-stu-id="024cb-205">Notice that the range is smaller than the `double` type.</span></span> <span data-ttu-id="024cb-206">Вы можете убедиться в повышении точности при использовании типа decimal, выполнив следующий код:</span><span class="sxs-lookup"><span data-stu-id="024cb-206">You can see the greater precision with the decimal type by trying the following code:</span></span>

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

<span data-ttu-id="024cb-207">Суффикс `M` возле чисел указывает, что для константы должен использоваться тип `decimal`.</span><span class="sxs-lookup"><span data-stu-id="024cb-207">The `M` suffix on the numbers is how you indicate that a constant should use the `decimal` type.</span></span>

<span data-ttu-id="024cb-208">Обратите внимание, что при вычислении с использованием типа decimal справа от запятой содержится больше цифр.</span><span class="sxs-lookup"><span data-stu-id="024cb-208">Notice that the math using the decimal type has more digits to the right of the decimal point.</span></span> 

<span data-ttu-id="024cb-209">***Задача***</span><span class="sxs-lookup"><span data-stu-id="024cb-209">***Challenge***</span></span>

<span data-ttu-id="024cb-210">Теперь, когда вы ознакомились с разными числовыми типами, напишите код, который позволяет вычислить площадь круга с радиусом 6,35 см.</span><span class="sxs-lookup"><span data-stu-id="024cb-210">Now that you've seen the different numeric types, write code that calculates the area of a circle whose radius is 2.50 inches.</span></span> <span data-ttu-id="024cb-211">Помните, что площадь круга равна квадрату радиуса, умноженному на число пи.</span><span class="sxs-lookup"><span data-stu-id="024cb-211">Remember that the area of a circle is the radius squared multiplied by PI.</span></span> <span data-ttu-id="024cb-212">Одно указание: C# содержит константы PI, <xref:System.Math.PI?displayProperty=nameWithType> , можно использовать для этого значения.</span><span class="sxs-lookup"><span data-stu-id="024cb-212">One hint: C# contains a constant for PI, <xref:System.Math.PI?displayProperty=nameWithType> that you can use for that value.</span></span> 

<span data-ttu-id="024cb-213">Вы можете проверить ответ путем [просматривая законченном примере код на GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span><span class="sxs-lookup"><span data-stu-id="024cb-213">You can check your answer by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)</span></span>

<span data-ttu-id="024cb-214">Если вы хотите, попробуйте выполните некоторые другие формулы.</span><span class="sxs-lookup"><span data-stu-id="024cb-214">Try some other formulas if you'd like.</span></span> 

<span data-ttu-id="024cb-215">Вы завершили краткое руководство «чисел в C#».</span><span class="sxs-lookup"><span data-stu-id="024cb-215">You've completed the "Numbers in C#" quick start.</span></span> <span data-ttu-id="024cb-216">Можно продолжить [ветвей и циклы](branches-and-loops-local.md) быстрый запуск в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="024cb-216">You can continue with the [Branches and loops](branches-and-loops-local.md) quick start in your own development environment.</span></span>

<span data-ttu-id="024cb-217">Дополнительные сведения о числах в C# см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="024cb-217">You can learn more about numbers in C# in the following topics:</span></span>

<span data-ttu-id="024cb-218">[Таблица целых типов](../language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="024cb-218">[Integral Types Table](../language-reference/keywords/integral-types-table.md) </span></span>  
<span data-ttu-id="024cb-219">[Таблица типов с плавающей запятой](../language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="024cb-219">[Floating-Point Types Table](../language-reference/keywords/floating-point-types-table.md) </span></span>  
<span data-ttu-id="024cb-220">[Таблица встроенных типов](../language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="024cb-220">[Built-In Types Table](../language-reference/keywords/built-in-types-table.md) </span></span>  
<span data-ttu-id="024cb-221">[Таблица неявных числовых преобразований](../language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="024cb-221">[Implicit Numeric Conversions Table](../language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
[<span data-ttu-id="024cb-222">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="024cb-222">Explicit Numeric Conversions Table</span></span>](../language-reference/keywords/explicit-numeric-conversions-table.md)

