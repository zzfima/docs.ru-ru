---
title: "Начало работы с F # в Visual Studio"
description: "Сведения об использовании языка F # в Visual Studio."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: 818bf50507a88e1d765da8d0505ed8da4790b71f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="e2d06-104">Начало работы с F # в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2d06-104">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="e2d06-105">F # и инструменты Visual F # поддерживаются в Интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2d06-105">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>  <span data-ttu-id="e2d06-106">Для начала следует [загрузите Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="e2d06-106">To begin, you should [download Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), if you haven't already.</span></span>  <span data-ttu-id="e2d06-107">В этой статье используется Visual Studio Community Edition 2017 г., но можно использовать F # с версией по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="e2d06-107">This article uses the Visual Studio 2017 Community Edition, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="e2d06-108">Установка F #</span><span class="sxs-lookup"><span data-stu-id="e2d06-108">Installing F#</span></span> #

<span data-ttu-id="e2d06-109">Если загрузка Visual Studio в первый раз, он сначала установить установщик Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2d06-109">If you're downloading Visual Studio for the first time, it will first install the Visual Studio installer.</span></span>  <span data-ttu-id="e2d06-110">Установка любой версии Visual Studio 2017 г установщика.</span><span class="sxs-lookup"><span data-stu-id="e2d06-110">Install any version of Visual Studio 2017 from the installer.</span></span> <span data-ttu-id="e2d06-111">Если вы уже настроили ее установки, нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="e2d06-111">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="e2d06-112">Далее вы увидите список рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="e2d06-112">You'll next see a list of Workloads.</span></span> <span data-ttu-id="e2d06-113">Вы можете установить F # через любой из следующих рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="e2d06-113">You can install F# through any of the following workloads:</span></span>

|<span data-ttu-id="e2d06-114">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="e2d06-114">Workload</span></span>|<span data-ttu-id="e2d06-115">Действие</span><span class="sxs-lookup"><span data-stu-id="e2d06-115">Action</span></span>|
|--------|------|
| <span data-ttu-id="e2d06-116">Кроссплатформенная разработка .NET Core</span><span class="sxs-lookup"><span data-stu-id="e2d06-116">.NET Core cross-platform development</span></span> | <span data-ttu-id="e2d06-117">По умолчанию устанавливается вмешательство - F #</span><span class="sxs-lookup"><span data-stu-id="e2d06-117">No action - F# is installed by default</span></span> |
| <span data-ttu-id="e2d06-118">ASP.NET и веб-разработка</span><span class="sxs-lookup"><span data-stu-id="e2d06-118">ASP.NET and web development</span></span> | <span data-ttu-id="e2d06-119">По умолчанию устанавливается вмешательство - F #</span><span class="sxs-lookup"><span data-stu-id="e2d06-119">No action - F# is installed by default</span></span> |
| <span data-ttu-id="e2d06-120">Разработка для Azure</span><span class="sxs-lookup"><span data-stu-id="e2d06-120">Azure development</span></span> | <span data-ttu-id="e2d06-121">По умолчанию устанавливается вмешательство - F #</span><span class="sxs-lookup"><span data-stu-id="e2d06-121">No action - F# is installed by default</span></span> |
| <span data-ttu-id="e2d06-122">Разработка мобильных приложений на платформе .NET</span><span class="sxs-lookup"><span data-stu-id="e2d06-122">Mobile development with .NET</span></span> | <span data-ttu-id="e2d06-123">По умолчанию устанавливается вмешательство - F #</span><span class="sxs-lookup"><span data-stu-id="e2d06-123">No action - F# is installed by default</span></span> |
| <span data-ttu-id="e2d06-124">Приложения для обработки и анализа данных и аналитические приложения</span><span class="sxs-lookup"><span data-stu-id="e2d06-124">Data science and analytical applications</span></span> | <span data-ttu-id="e2d06-125">По умолчанию устанавливается вмешательство - F #</span><span class="sxs-lookup"><span data-stu-id="e2d06-125">No action - F# is installed by default</span></span> |
| <span data-ttu-id="e2d06-126">Разработка классических приложений .NET</span><span class="sxs-lookup"><span data-stu-id="e2d06-126">.NET desktop development</span></span> | <span data-ttu-id="e2d06-127">Выберите **поддержки рабочего стола языка F #** с правой стороны</span><span class="sxs-lookup"><span data-stu-id="e2d06-127">Select **F# desktop language support** from the right-hand side</span></span> |
| <span data-ttu-id="e2d06-128">Хранение и обработка данных</span><span class="sxs-lookup"><span data-stu-id="e2d06-128">Data storage and processing</span></span> | <span data-ttu-id="e2d06-129">Выберите **поддержки рабочего стола языка F #** с правой стороны</span><span class="sxs-lookup"><span data-stu-id="e2d06-129">Select **F# desktop language support** from the right-hand side</span></span> |

<span data-ttu-id="e2d06-130">Далее щелкните **изменить** в правом нижнем.</span><span class="sxs-lookup"><span data-stu-id="e2d06-130">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="e2d06-131">Будут установлены все компоненты, которые вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="e2d06-131">This will install everything you have selected.</span></span>  <span data-ttu-id="e2d06-132">Затем можно открыть Visual Studio 2017 г. с поддержкой языка F #, щелкнув **запуска**.</span><span class="sxs-lookup"><span data-stu-id="e2d06-132">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="e2d06-133">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="e2d06-133">Creating a console application</span></span>

<span data-ttu-id="e2d06-134">Одним из основных проектов в Visual Studio является консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="e2d06-134">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="e2d06-135">Вот как это делается.</span><span class="sxs-lookup"><span data-stu-id="e2d06-135">Here's how to do it.</span></span>  <span data-ttu-id="e2d06-136">После открытия Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="e2d06-136">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="e2d06-137">На **файл** последовательно выберите пункты **New**, а затем выберите **проекта**.</span><span class="sxs-lookup"><span data-stu-id="e2d06-137">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="e2d06-138">В командлет New Project диалоговое окно, в разделе **шаблоны**, вы увидите **Visual F #**.</span><span class="sxs-lookup"><span data-stu-id="e2d06-138">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="e2d06-139">Выберите этот параметр, чтобы показать шаблонов F #.</span><span class="sxs-lookup"><span data-stu-id="e2d06-139">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="e2d06-140">Выберите либо **.NET Core консольного приложения** или **консольного приложения**.</span><span class="sxs-lookup"><span data-stu-id="e2d06-140">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="e2d06-141">Выберите **хорошо** кнопку, чтобы создать проект F #!</span><span class="sxs-lookup"><span data-stu-id="e2d06-141">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="e2d06-142">Теперь вы увидите проекта F # в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="e2d06-142">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="e2d06-143">Создание кода</span><span class="sxs-lookup"><span data-stu-id="e2d06-143">Writing your code</span></span>

<span data-ttu-id="e2d06-144">Давайте начнем путем написания кода сначала.</span><span class="sxs-lookup"><span data-stu-id="e2d06-144">Let's get started by writing some code first.</span></span>  <span data-ttu-id="e2d06-145">Убедитесь, что `Program.fs` файл открыт, а затем замените его содержимое следующим:</span><span class="sxs-lookup"><span data-stu-id="e2d06-145">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="e2d06-146">В приведенном выше примере, функция `square` был определен принимающий входных данных с именем `x` и умножает его самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="e2d06-146">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="e2d06-147">Поскольку в языке F # используется [вывод типа](../language-reference/type-inference.md), тип `x` указывать не требуется.</span><span class="sxs-lookup"><span data-stu-id="e2d06-147">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="e2d06-148">Компилятор F # понимает типы, где умножение является допустимым и будет назначать тип для `x` зависимости от способа `square` вызывается.</span><span class="sxs-lookup"><span data-stu-id="e2d06-148">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="e2d06-149">Если навести на `square`, вы увидите следующее:</span><span class="sxs-lookup"><span data-stu-id="e2d06-149">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="e2d06-150">Это значение, называемое сигнатура типа функции.</span><span class="sxs-lookup"><span data-stu-id="e2d06-150">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="e2d06-151">Оно может быть прочитано следующим образом: «квадратная является функция, которая принимает целое число с именем x и создает целое число».</span><span class="sxs-lookup"><span data-stu-id="e2d06-151">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="e2d06-152">Обратите внимание, что компилятор присваивает `square` `int` тип сейчас - это, поскольку умножения, не является универсальным через *все* типов, а вместо этого универсального между закрытый набор типов.</span><span class="sxs-lookup"><span data-stu-id="e2d06-152">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="e2d06-153">Компилятор F # выбрать `int` это точка, но он позволяет корректировать сигнатура типа при вызове метода `square` в другой тип входных данных, таких как `float`.</span><span class="sxs-lookup"><span data-stu-id="e2d06-153">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="e2d06-154">Другой функции `main`, определения, отмеченный `EntryPoint` атрибут, чтобы информировать компилятор F #, выполнение программы должны начать прямо отсюда.</span><span class="sxs-lookup"><span data-stu-id="e2d06-154">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="e2d06-155">Следует, то же соглашение, что и другие [языки программирования C-стиле](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), где аргументы командной строки могут быть переданы в эту функцию и возвращают целочисленный код (обычно `0`).</span><span class="sxs-lookup"><span data-stu-id="e2d06-155">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="e2d06-156">В этой функции, которая вызывается метод `square` функцию с аргументом `12`.</span><span class="sxs-lookup"><span data-stu-id="e2d06-156">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="e2d06-157">Компилятор F #, затем назначает тип `square` быть `int -> int` (то есть функция, которая принимает `int` и создает `int`).</span><span class="sxs-lookup"><span data-stu-id="e2d06-157">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="e2d06-158">Вызов `printfn` является форматированный функцию печати, в которой используется строка формата, похожи на языки программирования C-стиле, параметры, которые соответствуют алгоритмам, заданным в строке формата, а затем выводит результат и новую строку.</span><span class="sxs-lookup"><span data-stu-id="e2d06-158">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="e2d06-159">Выполнение кода</span><span class="sxs-lookup"><span data-stu-id="e2d06-159">Running your code</span></span>

<span data-ttu-id="e2d06-160">Можно запустить код и просмотреть результаты, нажав клавишу **ctrl-f5**.</span><span class="sxs-lookup"><span data-stu-id="e2d06-160">You can run the code and see results by pressing **ctrl-f5**.</span></span>  <span data-ttu-id="e2d06-161">Это будет выполняться программа без отладки и позволяет вам быстро просматривать результаты.</span><span class="sxs-lookup"><span data-stu-id="e2d06-161">This will run the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="e2d06-162">Кроме того, можно выбрать **отладки** меню верхнего уровня элемент в Visual Studio, выбрав **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="e2d06-162">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="e2d06-163">Теперь вы увидите следующее напечатаны в окне консоли, всплывает Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="e2d06-163">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="e2d06-164">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="e2d06-164">Congratulations!</span></span>  <span data-ttu-id="e2d06-165">Создания первого проекта F # в Visual Studio, написаны функции F # распечатать результаты вызова этой функции и запустите проект и результатов.</span><span class="sxs-lookup"><span data-stu-id="e2d06-165">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="e2d06-166">С помощью F # Interactive</span><span class="sxs-lookup"><span data-stu-id="e2d06-166">Using F# Interactive</span></span>

<span data-ttu-id="e2d06-167">Одним из лучшие возможности Visual F # в Visual Studio для работы с проектами является интерактивное окно F #.</span><span class="sxs-lookup"><span data-stu-id="e2d06-167">One of the best features of the Visual F# tooling in Visual Studio is the F# Interactive Window.</span></span>  <span data-ttu-id="e2d06-168">Он позволяет отправить код по процессу, в которой можно вызвать этот код и просмотреть результат в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="e2d06-168">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="e2d06-169">Чтобы начать использовать его, выделите `square` функции, определенной в коде.</span><span class="sxs-lookup"><span data-stu-id="e2d06-169">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="e2d06-170">Затем, удерживая **Alt** ключа и нажмите клавишу **ввод**.</span><span class="sxs-lookup"><span data-stu-id="e2d06-170">Next, hold the **Alt** key and press **Enter**.</span></span>  <span data-ttu-id="e2d06-171">Это выполняет код в интерактивное окно F #.</span><span class="sxs-lookup"><span data-stu-id="e2d06-171">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="e2d06-172">Появится окно F # Interactive отображаются со следующими в ней:</span><span class="sxs-lookup"><span data-stu-id="e2d06-172">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="e2d06-173">В следующем примере показано сигнатуру функции для `square` функции, которую вы уже видели раньше при прохождении курсора над функции.</span><span class="sxs-lookup"><span data-stu-id="e2d06-173">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="e2d06-174">Поскольку `square` — теперь определен в F # Interactive процесса, его можно вызвать с разными значениями:</span><span class="sxs-lookup"><span data-stu-id="e2d06-174">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="e2d06-175">Это действие выполняет функцию, привязывающий результат к имени нового `it`и выводит тип и значение `it`.</span><span class="sxs-lookup"><span data-stu-id="e2d06-175">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="e2d06-176">Обратите внимание, вы должны завершить работу с каждой строки `;;`.</span><span class="sxs-lookup"><span data-stu-id="e2d06-176">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="e2d06-177">Это как F # Interactive знает после завершения вызова функции.</span><span class="sxs-lookup"><span data-stu-id="e2d06-177">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="e2d06-178">Можно также определять новые функции в F # Interactive:</span><span class="sxs-lookup"><span data-stu-id="e2d06-178">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="e2d06-179">Выше определения новую функцию `isOdd`, который принимает `int` и проверяет, является ли нечетное!</span><span class="sxs-lookup"><span data-stu-id="e2d06-179">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span> <span data-ttu-id="e2d06-180">Эта функция для просмотра возвращается с разными вводными данными.</span><span class="sxs-lookup"><span data-stu-id="e2d06-180">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="e2d06-181">Можно вызывать функции в вызовах функций:</span><span class="sxs-lookup"><span data-stu-id="e2d06-181">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="e2d06-182">Можно также использовать [оператор прямого канала](../language-reference/symbol-and-operator-reference/index.md) конвейерная передача значения в двух функций:</span><span class="sxs-lookup"><span data-stu-id="e2d06-182">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="e2d06-183">Оператор прямого канала и многое другое, рассматриваются в следующих занятиях рассматривается.</span><span class="sxs-lookup"><span data-stu-id="e2d06-183">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="e2d06-184">Это представление только в том, что можно сделать с F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="e2d06-184">This is only a glimpse into what you can do with F# Interactive.</span></span> <span data-ttu-id="e2d06-185">Для получения дополнительных сведений ознакомьтесь [интерактивного программирование на F #](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="e2d06-185">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2d06-186">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="e2d06-186">Next steps</span></span>

<span data-ttu-id="e2d06-187">Если это еще не сделано, извлечь [обзор языка F #](../tour.md), который рассматриваются некоторые основные возможности языка F #.</span><span class="sxs-lookup"><span data-stu-id="e2d06-187">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="e2d06-188">Он приведен обзор некоторых возможностей F # и предоставить достаточно примеры кода можно скопировать в Visual Studio и запустить.</span><span class="sxs-lookup"><span data-stu-id="e2d06-188">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="e2d06-189">Существуют также некоторые полезные внешние ресурсы, которые можно использовать в демонстрации [руководство по F #](../index.md).</span><span class="sxs-lookup"><span data-stu-id="e2d06-189">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2d06-190">См. также</span><span class="sxs-lookup"><span data-stu-id="e2d06-190">See also</span></span>
 [<span data-ttu-id="e2d06-191">Visual F#</span><span class="sxs-lookup"><span data-stu-id="e2d06-191">Visual F#</span></span>](index.md)  
 [<span data-ttu-id="e2d06-192">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="e2d06-192">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="e2d06-193">Справочник по языку F #</span><span class="sxs-lookup"><span data-stu-id="e2d06-193">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="e2d06-194">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="e2d06-194">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="e2d06-195">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="e2d06-195">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
