---
title: "Краткое руководство - ветвей и lops - руководство по C#"
description: "В этом кратком руководстве о ветви и циклы можно написать код C# для изучения синтаксиса языка, поддерживающего условных ветвей и циклов для повторного выполнения инструкции."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4b077a29cf42072a93b054f50a13a4580ad54304
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2017
---
# <a name="branches-and-loops"></a><span data-ttu-id="f88ce-103">Ветви и циклы</span><span class="sxs-lookup"><span data-stu-id="f88ce-103">Branches and loops</span></span>

<span data-ttu-id="f88ce-104">В этом кратком руководстве объясняется, как написать код, который проверяет переменные и изменяет путь выполнения, на основе этих переменных.</span><span class="sxs-lookup"><span data-stu-id="f88ce-104">This quick start teaches you how to write code that examines variables and changes the execution path based on those variables.</span></span> <span data-ttu-id="f88ce-105">Написать код C# и просмотреть результаты компиляции и выполнения его.</span><span class="sxs-lookup"><span data-stu-id="f88ce-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="f88ce-106">Краткое руководство содержит ряд уроков, посвященные ветвления и циклические конструкции в C#.</span><span class="sxs-lookup"><span data-stu-id="f88ce-106">The quick start contains a series of lessons that explore branching and looping constructs in C#.</span></span> <span data-ttu-id="f88ce-107">В рамках этих занятий вы ознакомитесь с основами языка C#.</span><span class="sxs-lookup"><span data-stu-id="f88ce-107">These lessons teach you the fundamentals of the C# language.</span></span>

<span data-ttu-id="f88ce-108">В этом кратком руководстве предполагается, что вы машины, которые можно использовать для разработки приложений.</span><span class="sxs-lookup"><span data-stu-id="f88ce-108">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="f88ce-109">В разделе .NET [приступить к работе в течение 10 минут](https://www.microsoft.com/net/core) содержит инструкции по настройке в локальной среде разработки на Mac, ПК или Linux.</span><span class="sxs-lookup"><span data-stu-id="f88ce-109">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

## <a name="make-decisions-using-the-if-statement"></a><span data-ttu-id="f88ce-110">Принятия решений с помощью `if` инструкции</span><span class="sxs-lookup"><span data-stu-id="f88ce-110">Make decisions using the `if` statement</span></span>

<span data-ttu-id="f88ce-111">Создайте каталог с именем **краткое руководство ветвей**.</span><span class="sxs-lookup"><span data-stu-id="f88ce-111">Create a directory named **branches-quickstart**.</span></span> <span data-ttu-id="f88ce-112">Откройте этот каталог и выполните команду `dotnet new console -n BranchesAndLoops -o .`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-112">Make that the current directory and run `dotnet new console -n BranchesAndLoops -o .`.</span></span> <span data-ttu-id="f88ce-113">Эта команда создает новое консольное приложение .NET Core в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f88ce-113">This command creates a new .NET Core console application in the current directory.</span></span> 

<span data-ttu-id="f88ce-114">Откройте **Program.cs** в любом редакторе и замените строку `Console.Writeline("Hello World!");` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f88ce-114">Open **Program.cs** in your favorite editor, and replace the line `Console.Writeline("Hello World!");` with the following code:</span></span>

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

<span data-ttu-id="f88ce-115">Попробуйте использовать этот код, введя `dotnet run` в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="f88ce-115">Try this code by typing `dotnet run` in the your console window.</span></span> <span data-ttu-id="f88ce-116">Должно появиться сообщение «ответ больше, чем 10».</span><span class="sxs-lookup"><span data-stu-id="f88ce-116">You should see the message "The answer is greater than 10."</span></span> <span data-ttu-id="f88ce-117">Печать в консоль.</span><span class="sxs-lookup"><span data-stu-id="f88ce-117">printed to your console.</span></span>

<span data-ttu-id="f88ce-118">Измените объявление `b`, чтобы сумма была меньше 10:</span><span class="sxs-lookup"><span data-stu-id="f88ce-118">Modify the declaration of `b` so that the sum is less than 10:</span></span> 

```csharp
int b = 3;
```

<span data-ttu-id="f88ce-119">Тип `dotnet run` еще раз.</span><span class="sxs-lookup"><span data-stu-id="f88ce-119">Type `dotnet run` again.</span></span> <span data-ttu-id="f88ce-120">Так как ответ меньше 10, никакие данные не выводятся.</span><span class="sxs-lookup"><span data-stu-id="f88ce-120">Because the answer is less than 10, nothing is printed.</span></span> <span data-ttu-id="f88ce-121">Проверяемое **условие** имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="f88ce-121">The **condition** you're testing is false.</span></span> <span data-ttu-id="f88ce-122">У вас еще нет кода для выполнения, так как вы написали только одну из возможных ветвей для оператора `if` — ветвь true.</span><span class="sxs-lookup"><span data-stu-id="f88ce-122">You don't have any code to execute because you've only written one of the possible branches for an `if` statement: the true branch.</span></span>

> [!TIP]
> <span data-ttu-id="f88ce-123">Вероятнее всего, при изучении C# (как и любого другого языка программирования) вы будете допускать ошибки в коде.</span><span class="sxs-lookup"><span data-stu-id="f88ce-123">As you explore C# (or any programming language), you'll make mistakes when you write code.</span></span> <span data-ttu-id="f88ce-124">Компилятор находит и отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f88ce-124">The compiler will find and report the errors.</span></span> <span data-ttu-id="f88ce-125">Внимательно посмотрите на вывод ошибок и кода, вызвавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="f88ce-125">Look closely the the error output and the code that generated the error.</span></span> <span data-ttu-id="f88ce-126">Ошибка compler обычно может помочь найти проблемы.</span><span class="sxs-lookup"><span data-stu-id="f88ce-126">The compler error can usually help you find the problem.</span></span> 

<span data-ttu-id="f88ce-127">В первом примере показывает возможности `if` и логические значения.</span><span class="sxs-lookup"><span data-stu-id="f88ce-127">This first sample shows the power of `if` and Boolean types.</span></span> <span data-ttu-id="f88ce-128">Объект *логическое* является переменной, которая может иметь одно из двух значений: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-128">A *Boolean* is a variable that can have one of two values: `true` or `false`.</span></span> <span data-ttu-id="f88ce-129">C# определяет особый тип, `bool` для логические переменные.</span><span class="sxs-lookup"><span data-stu-id="f88ce-129">C# defines a special type, `bool` for Boolean variables.</span></span> <span data-ttu-id="f88ce-130">Оператор `if` проверяет значение `bool`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-130">The `if` statement checks the value of a `bool`.</span></span> <span data-ttu-id="f88ce-131">Если значение `true`, выполняется оператор, следующий после `if`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-131">When the value is `true`, the statement following the `if` executes.</span></span> <span data-ttu-id="f88ce-132">В противном случае он пропускается.</span><span class="sxs-lookup"><span data-stu-id="f88ce-132">Otherwise, it is skipped.</span></span> 

<span data-ttu-id="f88ce-133">Этот процесс проверки условий и выполнения операторов на основе этих условий предоставляет широкие возможности.</span><span class="sxs-lookup"><span data-stu-id="f88ce-133">This process of checking conditions and executing statements based on those conditions is very powerful.</span></span>


## <a name="make-if-and-else-work-together"></a><span data-ttu-id="f88ce-134">Объединение операторов if и else</span><span class="sxs-lookup"><span data-stu-id="f88ce-134">Make if and else work together</span></span>

<span data-ttu-id="f88ce-135">Чтобы выполнить разный код в ветвях true и false, создайте ветвь `else`, которая будет выполняться, если условие имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="f88ce-135">To execute different code in both the true and false branches, you create an `else` branch that executes when the condition is false.</span></span> <span data-ttu-id="f88ce-136">Выберите этот вариант.</span><span class="sxs-lookup"><span data-stu-id="f88ce-136">Try this.</span></span> <span data-ttu-id="f88ce-137">Добавьте две последние строки в приведенный ниже код к вашей `Main` метод (необходимо иметь первые четыре):</span><span class="sxs-lookup"><span data-stu-id="f88ce-137">Add the last two lines in the code below to your `Main` method (you should already have the first four):</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

<span data-ttu-id="f88ce-138">Оператор после ключевого слова `else` выполняется, только если проверяемое условие имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-138">The statement following the `else` keyword executes only when the condition being tested is `false`.</span></span> <span data-ttu-id="f88ce-139">Объединение `if` и `else` с логическими операторами условия предоставляет все возможности, необходимо обрабатывать как `true` и `false` условие.</span><span class="sxs-lookup"><span data-stu-id="f88ce-139">Combining `if` and `else` with Boolean conditions provides all the power you need to handle both a `true` and a `false` condition.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f88ce-140">Отступы под операторами `if` и `else` предназначены только для удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="f88ce-140">The indentation under the `if` and `else` statements is for human readers.</span></span>
> <span data-ttu-id="f88ce-141">В языке C# не обязательно ставить отступы или пробелы.</span><span class="sxs-lookup"><span data-stu-id="f88ce-141">The C# language doesn't treat indentation or whitespace as significant.</span></span> <span data-ttu-id="f88ce-142">Операторы после ключевого слова `if` или `else` будут выполняться на основе условия.</span><span class="sxs-lookup"><span data-stu-id="f88ce-142">The statement following the `if` or `else` keyword will be executed based on the condition.</span></span> <span data-ttu-id="f88ce-143">Все примеры в этом кратком руководстве выполните распространенная практика отступа строки на основании потока управления инструкций.</span><span class="sxs-lookup"><span data-stu-id="f88ce-143">All the samples in this quick start follow a common practice to indent lines based on the control flow of statements.</span></span>

<span data-ttu-id="f88ce-144">Так как отступ не обязателен, используйте скобки `{` и `}`, если нужно указать несколько операторов в блоке кода, который выполняется в зависимости от условий.</span><span class="sxs-lookup"><span data-stu-id="f88ce-144">Because indentation is not significant, you need to use `{` and `}` to indicate when you want more than one statement to be part of the block that executes conditionally.</span></span> <span data-ttu-id="f88ce-145">Программисты C# обычно используют эти фигурные скобки во всех предложениях `if` и `else`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-145">C# programmers typically use those braces on all `if` and `else` clauses.</span></span> <span data-ttu-id="f88ce-146">Следующий пример является таким же, как только что созданный.</span><span class="sxs-lookup"><span data-stu-id="f88ce-146">The following example is the same as the one you just created.</span></span> <span data-ttu-id="f88ce-147">Измените код, перечисленные выше, чтобы совпадал со следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f88ce-147">Modify your code above to match the following code:</span></span>

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> <span data-ttu-id="f88ce-148">Через rest в этом кратком руководстве, все примеры кода фигурные скобки, после принятия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="f88ce-148">Through the rest of this quick start, the code samples all include the braces, following accepted practices.</span></span>

<span data-ttu-id="f88ce-149">Вы можете протестировать более сложных условий.</span><span class="sxs-lookup"><span data-stu-id="f88ce-149">You can test more complicated conditions.</span></span> <span data-ttu-id="f88ce-150">Добавьте следующий код в вашей `Main` метод после кода, который вы написали в данный момент:</span><span class="sxs-lookup"><span data-stu-id="f88ce-150">Add the following code in your `Main` method after the code you've written so far:</span></span>

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

<span data-ttu-id="f88ce-151">`&&` представляет оператор and.</span><span class="sxs-lookup"><span data-stu-id="f88ce-151">The `&&` represents "and".</span></span> <span data-ttu-id="f88ce-152">То есть для выполнения оператора в ветви true оба условия должны иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="f88ce-152">It means both conditions must be true to execute the statement in the true branch.</span></span>  <span data-ttu-id="f88ce-153">В этих примерах также показано, что в каждой условной ветви можно задать несколько операторов. Нужно лишь заключить их в скобки `{` и `}`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-153">These examples also show that you can have multiple statements in each conditional branch, provided you enclose them in `{` and `}`.</span></span>

<span data-ttu-id="f88ce-154">Можно также использовать `||` для представления «или».</span><span class="sxs-lookup"><span data-stu-id="f88ce-154">You can also use  `||` to represent "or".</span></span> <span data-ttu-id="f88ce-155">Добавьте следующий код после ваши записи до сих:</span><span class="sxs-lookup"><span data-stu-id="f88ce-155">Add the following code after what you've written so far:</span></span>

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

<span data-ttu-id="f88ce-156">После завершения первого шага.</span><span class="sxs-lookup"><span data-stu-id="f88ce-156">You've finished the first step.</span></span> <span data-ttu-id="f88ce-157">Прежде чем перейти к следующему разделу, переместим текущий код в отдельный метод.</span><span class="sxs-lookup"><span data-stu-id="f88ce-157">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="f88ce-158">Это упростит начало работы с новым примером.</span><span class="sxs-lookup"><span data-stu-id="f88ce-158">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="f88ce-159">Переименуйте метод `Main` в `ExploreIf` и запишите новый метод `Main`, который вызывает `ExploreIf`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-159">Rename your `Main` method to `ExploreIf` and write a new `Main` method that calls `ExploreIf`.</span></span> <span data-ttu-id="f88ce-160">В результате ваш код должен выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f88ce-160">When you have finished, your code should look like this:</span></span>

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

<span data-ttu-id="f88ce-161">Закомментируйте вызов `ExploreIf()`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-161">Comment out the call to `ExploreIf()`.</span></span> <span data-ttu-id="f88ce-162">Это сделает менее перегружена, при работе в этом разделе выходные данные:</span><span class="sxs-lookup"><span data-stu-id="f88ce-162">It will make the output less cluttered as you work in this section:</span></span>

```csharp
//ExploreIf();
```

<span data-ttu-id="f88ce-163">`//` Запускает **комментарий** в C#.</span><span class="sxs-lookup"><span data-stu-id="f88ce-163">The `//` starts a **comment** in C#.</span></span> <span data-ttu-id="f88ce-164">Комментарии — это текст, который требуется сохранить в исходном коде, но не выполнять как код.</span><span class="sxs-lookup"><span data-stu-id="f88ce-164">Comments are any text you want to keep in your source code but not execute as code.</span></span> <span data-ttu-id="f88ce-165">Компилятор не создает исполняемого кода из комментариев.</span><span class="sxs-lookup"><span data-stu-id="f88ce-165">The compiler does not generate any executable code from comments.</span></span>

## <a name="use-loops-to-repeat-operations"></a><span data-ttu-id="f88ce-166">Использование циклов для повторения операций</span><span class="sxs-lookup"><span data-stu-id="f88ce-166">Use loops to repeat operations</span></span>

<span data-ttu-id="f88ce-167">В этом разделе используется **циклы** повторение инструкции.</span><span class="sxs-lookup"><span data-stu-id="f88ce-167">In this section you use **loops** to repeat statements.</span></span> <span data-ttu-id="f88ce-168">Попробуйте использовать этот код в вашей `Main` метод:</span><span class="sxs-lookup"><span data-stu-id="f88ce-168">Try this code in your `Main` method:</span></span>

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

<span data-ttu-id="f88ce-169">`while` Оператор проверяет условие и выполняет инструкцию или блок оператора, следующего `while`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-169">The `while` statement checks a condition and executes the statement or statement block following the `while`.</span></span> <span data-ttu-id="f88ce-170">Несколько раз, он проверяет условие и выполнения этих инструкций, пока условие равно false.</span><span class="sxs-lookup"><span data-stu-id="f88ce-170">It repeatedly checks the condition and executing those statements until the condition is false.</span></span>

<span data-ttu-id="f88ce-171">В этом примере представлен еще один новый оператор.</span><span class="sxs-lookup"><span data-stu-id="f88ce-171">There's one other new operator in this example.</span></span> <span data-ttu-id="f88ce-172">Объект `++` после переменной `counter` представляет собой оператор **инкремента**.</span><span class="sxs-lookup"><span data-stu-id="f88ce-172">The `++` after the `counter` variable is the **increment** operator.</span></span> <span data-ttu-id="f88ce-173">Он добавляет 1 к значению `counter` и сохраняет это значение в `counter` переменной.</span><span class="sxs-lookup"><span data-stu-id="f88ce-173">It adds 1 to the value of `counter` and stores that value in the `counter` variable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f88ce-174">Убедитесь, что `while` цикла условие примет значение false, при выполнении кода.</span><span class="sxs-lookup"><span data-stu-id="f88ce-174">Make sure that the `while` loop condition changes to false as you execute the code.</span></span> <span data-ttu-id="f88ce-175">В противном случае будет создан **бесконечный цикл**, в котором выполнение программы никогда не закончится.</span><span class="sxs-lookup"><span data-stu-id="f88ce-175">Otherwise, you create an **infinite loop** where your program never ends.</span></span> <span data-ttu-id="f88ce-176">Поскольку выполнение программы, чтобы завершить работу с помощью, не рассматривается в этом образце **CTRL-C** или другим способом.</span><span class="sxs-lookup"><span data-stu-id="f88ce-176">That is not demonstrated in this sample, because you have to force your program to quit using **CTRL-C** or other means.</span></span>

<span data-ttu-id="f88ce-177">В цикле `while` условие проверяется, прежде чем выполнить код, который следует после `while`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-177">The `while` loop tests the condition before executing the code following the `while`.</span></span> <span data-ttu-id="f88ce-178">А в цикле `do` ... `while` сначала выполняется код, а потом проверяется условие.</span><span class="sxs-lookup"><span data-stu-id="f88ce-178">The `do` ... `while` loop executes the code first, and then checks the condition.</span></span> <span data-ttu-id="f88ce-179">Действия, пока цикл показан в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="f88ce-179">The do while loop is shown in the following code:</span></span>

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

<span data-ttu-id="f88ce-180">Это `do` цикл и более ранним `while` цикла создавать такие же выходные данные.</span><span class="sxs-lookup"><span data-stu-id="f88ce-180">This `do` loop and the earlier `while` loop produce the same output.</span></span>

## <a name="work-with-the-for-loop"></a><span data-ttu-id="f88ce-181">Работа с циклом for</span><span class="sxs-lookup"><span data-stu-id="f88ce-181">Work with the for loop</span></span>

<span data-ttu-id="f88ce-182">**Для** цикла обычно используется в C#.</span><span class="sxs-lookup"><span data-stu-id="f88ce-182">The **for** loop is commonly used in C#.</span></span> <span data-ttu-id="f88ce-183">Попробуйте использовать этот код в метод Main():</span><span class="sxs-lookup"><span data-stu-id="f88ce-183">Try this code in your Main() method:</span></span>

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

<span data-ttu-id="f88ce-184">Этот цикл работает так же, как циклы `while` и `do`, использованные ранее.</span><span class="sxs-lookup"><span data-stu-id="f88ce-184">This does the same work as the `while` loop and the `do` loop you've already used.</span></span> <span data-ttu-id="f88ce-185">Оператор `for` состоит из трех частей, которые отвечают за его работу.</span><span class="sxs-lookup"><span data-stu-id="f88ce-185">The `for` statement has three parts that control how it works.</span></span> 

<span data-ttu-id="f88ce-186">Первая часть — **для инициализатора**: `for index = 0;` объявляет `index` переменной цикла и задает для ее начальное значение `0`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-186">The first part is the **for initializer**: `for index = 0;` declares that `index` is the loop variable, and sets its initial value to `0`.</span></span>

<span data-ttu-id="f88ce-187">Средняя часть — **для условия**: `index < 10` объявляет, что этот цикл `for` продолжает выполняться, пока значение счетчика меньше 10.</span><span class="sxs-lookup"><span data-stu-id="f88ce-187">The middle part is the **for condition**: `index < 10` declares that this `for` loop continues to execute as long as the value of counter is less than 10.</span></span>

<span data-ttu-id="f88ce-188">Последняя часть — **для итератора**: `index++` определяет, как изменится переменная цикла после выполнения блока, следующего после оператора `for`.</span><span class="sxs-lookup"><span data-stu-id="f88ce-188">The final part is the **for iterator**: `index++` specifies how to modify the loop variable after executing the block following the `for` statement.</span></span> <span data-ttu-id="f88ce-189">В нашем случае определяется, что значение `index` должно увеличиваться на 1 каждый раз, когда выполняется блок.</span><span class="sxs-lookup"><span data-stu-id="f88ce-189">Here, it specifies that `index` should be incremented by 1 each time the block executes.</span></span>

<span data-ttu-id="f88ce-190">Попробуйте сделать это самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f88ce-190">Experiment with these yourself.</span></span> <span data-ttu-id="f88ce-191">Попытайтесь выполнить следующие задания:</span><span class="sxs-lookup"><span data-stu-id="f88ce-191">Try each of the following:</span></span>

- <span data-ttu-id="f88ce-192">Измените инициализатор, чтобы цикл начинался с другого значения.</span><span class="sxs-lookup"><span data-stu-id="f88ce-192">Change the initializer to start at a different value.</span></span>
- <span data-ttu-id="f88ce-193">Измените условие, чтобы цикл заканчивался другим значением.</span><span class="sxs-lookup"><span data-stu-id="f88ce-193">Change the condition to stop at a different value.</span></span>

<span data-ttu-id="f88ce-194">По окончании попробуйте самостоятельно написать код, чтобы применить полученные знания.</span><span class="sxs-lookup"><span data-stu-id="f88ce-194">When you're done, let's move on to write some code yourself to use what you've learned.</span></span>

## <a name="combine-branches-and-loops"></a><span data-ttu-id="f88ce-195">Объединение ветвей и циклов</span><span class="sxs-lookup"><span data-stu-id="f88ce-195">Combine branches and loops</span></span>

<span data-ttu-id="f88ce-196">Теперь, когда вы ознакомились с оператором `if` и конструкциями цикла на языке C#, попытайтесь написать код C# для поиска суммы всех целых чисел от 1 до 20, которые делятся на 3.</span><span class="sxs-lookup"><span data-stu-id="f88ce-196">Now that you've seen the `if` statement and the looping constructs in the C# language, see if you can write C# code to find the sum of all integers 1 through 20 that are divisible by 3.</span></span>  <span data-ttu-id="f88ce-197">Вот несколько подсказок:</span><span class="sxs-lookup"><span data-stu-id="f88ce-197">Here are a few hints:</span></span>

- <span data-ttu-id="f88ce-198">оператор `%` позволяет получить остаток от операции деления;</span><span class="sxs-lookup"><span data-stu-id="f88ce-198">The `%` operator gives you the remainder of a division operation.</span></span>
- <span data-ttu-id="f88ce-199">`if` Инструкция дает условие, чтобы увидеть, если число должно быть частью суммы.</span><span class="sxs-lookup"><span data-stu-id="f88ce-199">The `if` statement gives you the condition to see if a number should be part of the sum.</span></span>
- <span data-ttu-id="f88ce-200">цикл `for` позволяет повторить последовательность шагов для всех чисел от 1 до 20.</span><span class="sxs-lookup"><span data-stu-id="f88ce-200">The `for` loop can help you repeat a series of steps for all the numbers 1 through 20.</span></span>

<span data-ttu-id="f88ce-201">Попробуйте самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="f88ce-201">Try it yourself.</span></span> <span data-ttu-id="f88ce-202">Затем проверьте результат.</span><span class="sxs-lookup"><span data-stu-id="f88ce-202">Then check how you did.</span></span> <span data-ttu-id="f88ce-203">Вы увидите один возможный ответ по [Просмотр полный код на GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span><span class="sxs-lookup"><span data-stu-id="f88ce-203">You can see one possible answer by [viewing the completed code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).</span></span>

<span data-ttu-id="f88ce-204">После завершения «ветвей и циклы» быстрый запуск.</span><span class="sxs-lookup"><span data-stu-id="f88ce-204">You've completed the "branches and loops" quick start.</span></span>

<span data-ttu-id="f88ce-205">Можно продолжить [массивы и коллекции](arrays-and-collections.md) быстрый запуск в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="f88ce-205">You can continue with the [Arrays and collections](arrays-and-collections.md) quick start in your own development environment.</span></span>

<span data-ttu-id="f88ce-206">Дополнительные сведения об этих понятиях см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f88ce-206">You can learn more about these concepts in these topics:</span></span>

<span data-ttu-id="f88ce-207">[if-else (справочник по C#)](../language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="f88ce-207">[If and else statement](../language-reference/keywords/if-else.md) </span></span>  
<span data-ttu-id="f88ce-208">[while (справочник по C#)](../language-reference/keywords/while.md) </span><span class="sxs-lookup"><span data-stu-id="f88ce-208">[While statement](../language-reference/keywords/while.md) </span></span>  
<span data-ttu-id="f88ce-209">[do (справочник по C#)](../language-reference/keywords/do.md) </span><span class="sxs-lookup"><span data-stu-id="f88ce-209">[Do statement](../language-reference/keywords/do.md) </span></span>  
[<span data-ttu-id="f88ce-210">for (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f88ce-210">For statement</span></span>](../language-reference/keywords/for.md)   
