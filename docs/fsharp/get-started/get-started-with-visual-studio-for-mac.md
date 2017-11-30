---
title: "Начало работы с F # в Visual Studio для Mac"
description: "Сведения об использовании языка F # в Visual Studio для Mac."
keywords: "visual f#, f#, функциональное программирование"
author: mizzle-mo
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: beee874e3a549531b520d4ac2150bc10dcab7725
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="095a7-104">Начало работы с F # в Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="095a7-104">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="095a7-105">F # и инструменты Visual F # поддерживаются в Visual Studio для Mac интегрированной среды разработки.</span><span class="sxs-lookup"><span data-stu-id="095a7-105">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span>  <span data-ttu-id="095a7-106">Для начала следует [скачать Visual Studio для Mac](https://www.visualstudio.com/downloads/download-visual-studio-vs), если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="095a7-106">To begin, you should [download Visual Studio for Mac](https://www.visualstudio.com/downloads/download-visual-studio-vs), if you haven't already.</span></span>  <span data-ttu-id="095a7-107">В этой статье используется сообщества Visual Studio 2017 г. для Mac, но можно использовать F # с версией по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="095a7-107">This article uses the Visual Studio Community 2017 for Mac, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="095a7-108">Установка F #</span><span class="sxs-lookup"><span data-stu-id="095a7-108">Installing F#</span></span> #

<span data-ttu-id="095a7-109">После загрузки Visual Studio для Mac, он предложит выбрать, следует установить.</span><span class="sxs-lookup"><span data-stu-id="095a7-109">After downloading Visual Studio for Mac, it will prompt you to choose what you want to install.</span></span>  <span data-ttu-id="095a7-110">Для целей данной статьи мы оставите значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="095a7-110">For the purposes of this article we will be leaving the defaults.</span></span>  <span data-ttu-id="095a7-111">В отличие от Visual Studio для Windows необходимо специально установить поддержку языка F #.</span><span class="sxs-lookup"><span data-stu-id="095a7-111">In contrast to Visual Studio for Windows, you do not need to specifically install F# support.</span></span>  <span data-ttu-id="095a7-112">Нажмите кнопку «Установить» для продолжения.</span><span class="sxs-lookup"><span data-stu-id="095a7-112">Press "Install" to proceed.</span></span>

<span data-ttu-id="095a7-113">После завершения установки, нажмите кнопку «Запустить Visual Studio».</span><span class="sxs-lookup"><span data-stu-id="095a7-113">After the install completes, choose "Start Visual Studio".</span></span>  <span data-ttu-id="095a7-114">Его можно также запустить через Finder на macOS.</span><span class="sxs-lookup"><span data-stu-id="095a7-114">You can also launch it through Finder on macOS.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="095a7-115">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="095a7-115">Creating a console application</span></span>

<span data-ttu-id="095a7-116">Одним из основных проектов в Visual Studio для Mac является консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="095a7-116">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="095a7-117">Вот как это делается.</span><span class="sxs-lookup"><span data-stu-id="095a7-117">Here's how to do it.</span></span>  <span data-ttu-id="095a7-118">После открытия Visual Studio для Mac:</span><span class="sxs-lookup"><span data-stu-id="095a7-118">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="095a7-119">На **файл** последовательно выберите пункты **новое решение**.</span><span class="sxs-lookup"><span data-stu-id="095a7-119">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="095a7-120">В диалоговом окне нового проекта существует 2 различных шаблонов для консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="095a7-120">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="095a7-121">Имеется один под другими -> .NET, который нацелен на .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="095a7-121">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="095a7-122">Второй шаблон находится в .NET Core -> приложения, который нацелен на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="095a7-122">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="095a7-123">Либо шаблон должен работать в данной статье.</span><span class="sxs-lookup"><span data-stu-id="095a7-123">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="095a7-124">В разделе консольное приложение C# в F # при необходимости измените.</span><span class="sxs-lookup"><span data-stu-id="095a7-124">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="095a7-125">Выберите **Далее** кнопку, чтобы переместить вперед!</span><span class="sxs-lookup"><span data-stu-id="095a7-125">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="095a7-126">Присвойте проекту имя и выберите нужный вариант для приложения.</span><span class="sxs-lookup"><span data-stu-id="095a7-126">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="095a7-127">Обратите внимание на панели предварительного просмотра, чтобы части экрана, отображающий структуру каталогов, которая будет создана на основании выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="095a7-127">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="095a7-128">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="095a7-128">Click **Create**.</span></span>  <span data-ttu-id="095a7-129">Теперь вы увидите проекта F # в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="095a7-129">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="095a7-130">Создание кода</span><span class="sxs-lookup"><span data-stu-id="095a7-130">Writing your code</span></span>

<span data-ttu-id="095a7-131">Давайте начнем путем написания кода сначала.</span><span class="sxs-lookup"><span data-stu-id="095a7-131">Let's get started by writing some code first.</span></span>  <span data-ttu-id="095a7-132">Убедитесь, что `Program.fs` файл открыт, а затем замените его содержимое следующим:</span><span class="sxs-lookup"><span data-stu-id="095a7-132">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="095a7-133">В приведенном выше примере, функция `square` был определен принимающий входных данных с именем `x` и умножает его самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="095a7-133">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="095a7-134">Поскольку в языке F # используется [вывод типа](../language-reference/type-inference.md), тип `x` указывать не требуется.</span><span class="sxs-lookup"><span data-stu-id="095a7-134">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="095a7-135">Компилятор F # понимает типы, где умножение является допустимым и будет назначать тип для `x` зависимости от способа `square` вызывается.</span><span class="sxs-lookup"><span data-stu-id="095a7-135">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="095a7-136">Если навести на `square`, вы увидите следующее:</span><span class="sxs-lookup"><span data-stu-id="095a7-136">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="095a7-137">Это значение, называемое сигнатура типа функции.</span><span class="sxs-lookup"><span data-stu-id="095a7-137">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="095a7-138">Оно может быть прочитано следующим образом: «квадратная является функция, которая принимает целое число с именем x и создает целое число».</span><span class="sxs-lookup"><span data-stu-id="095a7-138">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="095a7-139">Обратите внимание, что компилятор присваивает `square` `int` тип сейчас - это, поскольку умножения, не является универсальным через *все* типов, а вместо этого универсального между закрытый набор типов.</span><span class="sxs-lookup"><span data-stu-id="095a7-139">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="095a7-140">Компилятор F # выбрать `int` это точка, но он позволяет корректировать сигнатура типа при вызове метода `square` в другой тип входных данных, таких как `float`.</span><span class="sxs-lookup"><span data-stu-id="095a7-140">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="095a7-141">Другой функции `main`, определения, отмеченный `EntryPoint` атрибут, чтобы информировать компилятор F #, выполнение программы должны начать прямо отсюда.</span><span class="sxs-lookup"><span data-stu-id="095a7-141">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="095a7-142">Следует, то же соглашение, что и другие [языки программирования C-стиле](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), где аргументы командной строки могут быть переданы в эту функцию и возвращают целочисленный код (обычно `0`).</span><span class="sxs-lookup"><span data-stu-id="095a7-142">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="095a7-143">В этой функции, которая вызывается метод `square` функцию с аргументом `12`.</span><span class="sxs-lookup"><span data-stu-id="095a7-143">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="095a7-144">Компилятор F #, затем назначает тип `square` быть `int -> int` (то есть функция, которая принимает `int` и создает `int`).</span><span class="sxs-lookup"><span data-stu-id="095a7-144">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="095a7-145">Вызов `printfn` является форматированный функцию печати, в которой используется строка формата, похожи на языки программирования C-стиле, параметры, которые соответствуют алгоритмам, заданным в строке формата, а затем выводит результат и новую строку.</span><span class="sxs-lookup"><span data-stu-id="095a7-145">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="095a7-146">Выполнение кода</span><span class="sxs-lookup"><span data-stu-id="095a7-146">Running your code</span></span>

<span data-ttu-id="095a7-147">Можно запустить код и просмотреть результаты, щелкнув **запуска** меню верхнего уровня и затем **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="095a7-147">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="095a7-148">Это будет выполняться программа без отладки и позволяет вам быстро просматривать результаты.</span><span class="sxs-lookup"><span data-stu-id="095a7-148">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="095a7-149">Теперь вы увидите следующее напечатаны в окне консоли, всплывает Visual Studio для Mac:</span><span class="sxs-lookup"><span data-stu-id="095a7-149">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="095a7-150">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="095a7-150">Congratulations!</span></span>  <span data-ttu-id="095a7-151">Создания первого проекта F # в Visual Studio для Mac, написаны функции F # распечатать результаты вызова этой функции и запустите проект и результатов.</span><span class="sxs-lookup"><span data-stu-id="095a7-151">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="095a7-152">С помощью F # Interactive</span><span class="sxs-lookup"><span data-stu-id="095a7-152">Using F# Interactive</span></span>

<span data-ttu-id="095a7-153">Одна из наиболее функций Visual F # для работы с проектами в Visual Studio для Mac — интерактивное окно F #.</span><span class="sxs-lookup"><span data-stu-id="095a7-153">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="095a7-154">Он позволяет отправить код по процессу, в которой можно вызвать этот код и просмотреть результат в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="095a7-154">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="095a7-155">Чтобы начать использовать его, выделите `square` функции, определенной в коде.</span><span class="sxs-lookup"><span data-stu-id="095a7-155">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="095a7-156">Нажмите кнопку **изменить** меню верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="095a7-156">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="095a7-157">Затем выберите **отправить выделение в F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="095a7-157">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="095a7-158">Это выполняет код в интерактивное окно F #.</span><span class="sxs-lookup"><span data-stu-id="095a7-158">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="095a7-159">Или щелкните выделение правой кнопкой мыши и выберите **отправить выделение в F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="095a7-159">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="095a7-160">Появится окно F # Interactive отображаются со следующими в ней:</span><span class="sxs-lookup"><span data-stu-id="095a7-160">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="095a7-161">В следующем примере показано сигнатуру функции для `square` функции, которую вы уже видели раньше при прохождении курсора над функции.</span><span class="sxs-lookup"><span data-stu-id="095a7-161">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="095a7-162">Поскольку `square` — теперь определен в F # Interactive процесса, его можно вызвать с разными значениями:</span><span class="sxs-lookup"><span data-stu-id="095a7-162">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="095a7-163">Это действие выполняет функцию, привязывающий результат к имени нового `it`и выводит тип и значение `it`.</span><span class="sxs-lookup"><span data-stu-id="095a7-163">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="095a7-164">Обратите внимание, вы должны завершить работу с каждой строки `;;`.</span><span class="sxs-lookup"><span data-stu-id="095a7-164">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="095a7-165">Это как F # Interactive знает после завершения вызова функции.</span><span class="sxs-lookup"><span data-stu-id="095a7-165">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="095a7-166">Можно также определять новые функции в F # Interactive:</span><span class="sxs-lookup"><span data-stu-id="095a7-166">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="095a7-167">Выше определения новую функцию `isOdd`, который принимает `int` и проверяет, является ли нечетное!</span><span class="sxs-lookup"><span data-stu-id="095a7-167">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="095a7-168">Эта функция для просмотра возвращается с разными вводными данными.</span><span class="sxs-lookup"><span data-stu-id="095a7-168">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="095a7-169">Можно вызывать функции в вызовах функций:</span><span class="sxs-lookup"><span data-stu-id="095a7-169">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="095a7-170">Можно также использовать [оператор прямого канала](../language-reference/symbol-and-operator-reference/index.md) конвейерная передача значения в двух функций:</span><span class="sxs-lookup"><span data-stu-id="095a7-170">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="095a7-171">Оператор прямого канала и многое другое, рассматриваются в следующих занятиях рассматривается.</span><span class="sxs-lookup"><span data-stu-id="095a7-171">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="095a7-172">Это представление только в том, что можно сделать с F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="095a7-172">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="095a7-173">Для получения дополнительных сведений ознакомьтесь [интерактивного программирование на F #](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="095a7-173">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="095a7-174">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="095a7-174">Next steps</span></span>

<span data-ttu-id="095a7-175">Если это еще не сделано, извлечь [обзор языка F #](../tour.md), который рассматриваются некоторые основные возможности языка F #.</span><span class="sxs-lookup"><span data-stu-id="095a7-175">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="095a7-176">Он приведен обзор некоторых возможностей F # и предоставить достаточно примеры кода можно скопировать в Visual Studio для Mac и запустить.</span><span class="sxs-lookup"><span data-stu-id="095a7-176">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="095a7-177">Существуют также некоторые полезные внешние ресурсы, которые можно использовать в демонстрации [руководство по F #](../index.md).</span><span class="sxs-lookup"><span data-stu-id="095a7-177">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="095a7-178">См. также</span><span class="sxs-lookup"><span data-stu-id="095a7-178">See also</span></span>
 [<span data-ttu-id="095a7-179">Visual F#</span><span class="sxs-lookup"><span data-stu-id="095a7-179">Visual F#</span></span>](../index.md)  
 [<span data-ttu-id="095a7-180">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="095a7-180">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="095a7-181">Справочник по языку F #</span><span class="sxs-lookup"><span data-stu-id="095a7-181">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="095a7-182">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="095a7-182">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="095a7-183">Справочник символов и операторов</span><span class="sxs-lookup"><span data-stu-id="095a7-183">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
