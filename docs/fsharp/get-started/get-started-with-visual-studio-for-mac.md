---
title: 'Начало работы с F # в Visual Studio для Mac'
description: 'Сведения об использовании F # с помощью Visual Studio для Mac.'
ms.date: 07/03/2018
ms.openlocfilehash: 6aceec299c29e04aecd7999cd1dda6a56dd2779a
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785535"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="df703-103">Начало работы с F # в Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="df703-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="df703-104">F # и инструментария Visual F # поддерживаются в Visual Studio для Mac интегрированной среды разработки.</span><span class="sxs-lookup"><span data-stu-id="df703-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="df703-105">Убедитесь, что у вас есть [Visual Studio для Mac установлен](install-fsharp.md#install-f-with-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="df703-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="df703-106">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="df703-106">Creating a console application</span></span>

<span data-ttu-id="df703-107">Одним из основных проектов в Visual Studio для Mac — это консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="df703-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="df703-108">Вот как это делается.</span><span class="sxs-lookup"><span data-stu-id="df703-108">Here's how to do it.</span></span>  <span data-ttu-id="df703-109">После открытия Visual Studio для Mac:</span><span class="sxs-lookup"><span data-stu-id="df703-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="df703-110">На **файл** последовательно выберите пункты **новое решение**.</span><span class="sxs-lookup"><span data-stu-id="df703-110">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="df703-111">В диалоговом окне нового проекта существует 2 различных шаблонов для консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="df703-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="df703-112">Имеется один под другими "->".NET, предназначенный для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df703-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="df703-113">Другие шаблон находится в .NET Core "->" приложения, который нацелен на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df703-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="df703-114">Либо они должны работать в этой статье.</span><span class="sxs-lookup"><span data-stu-id="df703-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="df703-115">В разделе консольное приложение C# на F # при необходимости измените.</span><span class="sxs-lookup"><span data-stu-id="df703-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="df703-116">Выберите **Далее** кнопки для перемещения вперед!</span><span class="sxs-lookup"><span data-stu-id="df703-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="df703-117">Присвойте проекту имя и выберите нужный вариант для приложения.</span><span class="sxs-lookup"><span data-stu-id="df703-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="df703-118">Обратите внимание, что, области просмотра по краю экрана, отображающий структура каталогов, которая будет создана с учетом выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="df703-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="df703-119">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="df703-119">Click **Create**.</span></span>  <span data-ttu-id="df703-120">Теперь вы увидите проекта F # в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="df703-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="df703-121">Написание кода</span><span class="sxs-lookup"><span data-stu-id="df703-121">Writing your code</span></span>

<span data-ttu-id="df703-122">Давайте начнем сначала пишет некоторый код.</span><span class="sxs-lookup"><span data-stu-id="df703-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="df703-123">Убедитесь, что `Program.fs` файл открыт и замените его содержимое следующим:</span><span class="sxs-lookup"><span data-stu-id="df703-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="df703-124">В предыдущем примере кода, функция `square` был определен который принимает ввод с именем `x` и умножает его самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="df703-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="df703-125">Так как F # использует [вывод типа](../language-reference/type-inference.md), тип `x` не должны быть указаны.</span><span class="sxs-lookup"><span data-stu-id="df703-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="df703-126">Компилятор F # понимает типы, где умножение является допустимым и будет назначать тип для `x` зависит `square` вызывается.</span><span class="sxs-lookup"><span data-stu-id="df703-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="df703-127">Если навести `square`, вы должны увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="df703-127">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="df703-128">Это связано с так называемой сигнатура типа функции.</span><span class="sxs-lookup"><span data-stu-id="df703-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="df703-129">Может быть прочитан следующим образом: «квадрата является функция, которая принимает целое число с именем x и создает целое число».</span><span class="sxs-lookup"><span data-stu-id="df703-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="df703-130">Обратите внимание, что компилятор обеспечивал `square` `int` тип сейчас - это обусловлено умножения, не является универсальным через *все* типы, но довольно универсален через набор закрытых типов.</span><span class="sxs-lookup"><span data-stu-id="df703-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="df703-131">Компилятор F # выбраны `int` это точка, но он настроит сигнатуре типа при вызове метода `square` с другим ввода типа, например `float`.</span><span class="sxs-lookup"><span data-stu-id="df703-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="df703-132">Другую функцию `main`, определяется, который дополняется `EntryPoint` атрибут для указания компилятору F #, выполнение программы следует начать с этого.</span><span class="sxs-lookup"><span data-stu-id="df703-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="df703-133">Его следует тому же образцу что и другие [языков программирования в стиле C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), где эту функцию можно передать аргументы командной строки и возвращается код целого числа (обычно `0`).</span><span class="sxs-lookup"><span data-stu-id="df703-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="df703-134">В этой функции, мы вызываем `square` функцию с аргументом `12`.</span><span class="sxs-lookup"><span data-stu-id="df703-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="df703-135">Компилятор F # затем назначает тип `square` быть `int -> int` (то есть функция, которая принимает `int` и создает `int`).</span><span class="sxs-lookup"><span data-stu-id="df703-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="df703-136">Вызов `printfn` является форматированный печати функция, которая использует строку формата, аналогичную языков программирования C-стиля, параметры, которые соответствуют заданным в строке формата, а затем распечатывает результат и новую строку.</span><span class="sxs-lookup"><span data-stu-id="df703-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="df703-137">Выполнение кода</span><span class="sxs-lookup"><span data-stu-id="df703-137">Running your code</span></span>

<span data-ttu-id="df703-138">Можно выполнить код и увидеть результаты, щелкнув **запуска** в меню верхнего уровня и затем **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="df703-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="df703-139">Это будет запустить программу без отладки и дает возможность видеть результаты.</span><span class="sxs-lookup"><span data-stu-id="df703-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="df703-140">Теперь вы увидите следующие напечатаны в окне консоли, подчеркнутые Visual Studio для Mac:</span><span class="sxs-lookup"><span data-stu-id="df703-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="df703-141">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="df703-141">Congratulations!</span></span>  <span data-ttu-id="df703-142">Вы создали первый проект F # в Visual Studio для Mac, написаны функция F #, распечатать результаты вызова этой функции и запустите проект, чтобы увидеть некоторые результаты.</span><span class="sxs-lookup"><span data-stu-id="df703-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="df703-143">Использование F # Interactive</span><span class="sxs-lookup"><span data-stu-id="df703-143">Using F# Interactive</span></span>

<span data-ttu-id="df703-144">Одним из лучших функций Visual F # инструменты Visual Studio для Mac является интерактивным окном F #.</span><span class="sxs-lookup"><span data-stu-id="df703-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="df703-145">Он позволяет отравленных кода к процессу, где можно вызвать этот исходный текст и просмотреть результат в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="df703-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="df703-146">Чтобы начать использовать его, выделите `square` функции, определенной в коде.</span><span class="sxs-lookup"><span data-stu-id="df703-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="df703-147">Далее щелкните **изменить** в меню верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="df703-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="df703-148">Далее выберите **Отправить выбранный фрагмент в F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="df703-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="df703-149">Это выполняет код в интерактивном окне F #.</span><span class="sxs-lookup"><span data-stu-id="df703-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="df703-150">Кроме того, можно щелкнуть его правой кнопкой мыши и выбрать **Отправить выбранный фрагмент в F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="df703-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="df703-151">Вы должны увидеть окно F # Interactive отображаются со следующими в нем:</span><span class="sxs-lookup"><span data-stu-id="df703-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="df703-152">Это показывает сигнатуру функции для `square` функцию, которую вы уже видели при наведении функции.</span><span class="sxs-lookup"><span data-stu-id="df703-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="df703-153">Так как `square` — теперь определен в F # Interactive процесса, его можно вызвать с разными значениями:</span><span class="sxs-lookup"><span data-stu-id="df703-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="df703-154">Это выполняет функцию, связывает результаты с новым именем `it`и выводится тип и значение `it`.</span><span class="sxs-lookup"><span data-stu-id="df703-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="df703-155">Обратите внимание, что необходимо завершить каждая строка начинается с `;;`.</span><span class="sxs-lookup"><span data-stu-id="df703-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="df703-156">Это, как F # Interactive знает после завершения вызова функции.</span><span class="sxs-lookup"><span data-stu-id="df703-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="df703-157">Можно также определить новые функции в F # Interactive:</span><span class="sxs-lookup"><span data-stu-id="df703-157">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="df703-158">Оно определяется новая функция, `isOdd`, который принимает `int` и проверяет, находится ли он нечетное!</span><span class="sxs-lookup"><span data-stu-id="df703-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="df703-159">Можно вызвать эту функцию для см. в разделе, он возвращает с разными входными данными.</span><span class="sxs-lookup"><span data-stu-id="df703-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="df703-160">Можно вызывать функции в вызовах функций:</span><span class="sxs-lookup"><span data-stu-id="df703-160">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="df703-161">Можно также использовать [оператор прямого канала](../language-reference/symbol-and-operator-reference/index.md) конвейерная передача значения в двух функций:</span><span class="sxs-lookup"><span data-stu-id="df703-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="df703-162">Оператор прямого канала и многое другое, рассматриваются в последующих руководствах.</span><span class="sxs-lookup"><span data-stu-id="df703-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="df703-163">Это только нечто действий, выполняемых с помощью F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="df703-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="df703-164">Чтобы узнать больше, ознакомьтесь с [интерактивных программирование с использованием F #](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="df703-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="df703-165">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="df703-165">Next steps</span></span>

<span data-ttu-id="df703-166">Если это еще не сделано, см. статью [обзор языка F #](../tour.md), где приведены некоторые основные возможности языка F #.</span><span class="sxs-lookup"><span data-stu-id="df703-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="df703-167">Он будет дам обзор некоторых возможностей языка F # и предоставляет примеры кода можно в полной мере, можно скопировать в Visual Studio для Mac и запустить.</span><span class="sxs-lookup"><span data-stu-id="df703-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="df703-168">Существуют также некоторые полезные внешние ресурсы, которые можно использовать, показывавшие в [руководство по F #](../index.md).</span><span class="sxs-lookup"><span data-stu-id="df703-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="df703-169">См. также</span><span class="sxs-lookup"><span data-stu-id="df703-169">See also</span></span>

- [<span data-ttu-id="df703-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="df703-170">Visual F#</span></span>](../index.md)  
- [<span data-ttu-id="df703-171">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="df703-171">Tour of F#</span></span>](../tour.md)  
- [<span data-ttu-id="df703-172">Справочник по языку F #</span><span class="sxs-lookup"><span data-stu-id="df703-172">F# language reference</span></span>](../language-reference/index.md)  
- [<span data-ttu-id="df703-173">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="df703-173">Type inference</span></span>](../language-reference/type-inference.md)  
- [<span data-ttu-id="df703-174">Справочник символов и оператор</span><span class="sxs-lookup"><span data-stu-id="df703-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
