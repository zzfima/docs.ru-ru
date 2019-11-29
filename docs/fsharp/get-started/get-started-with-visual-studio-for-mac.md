---
title: Начало работы с F# в Visual Studio для Mac
description: Узнайте, как использовать F# с Visual Studio для Mac.
ms.date: 07/03/2018
ms.openlocfilehash: cd45ab9c59cef76e4bf85a93f39d8e2ee063d200
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552370"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="7d1d1-103">Начало работы с F# в Visual Studio для Mac</span><span class="sxs-lookup"><span data-stu-id="7d1d1-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="7d1d1-104">F#и визуальные F# средства поддерживаются в интегрированной среде разработки Visual Studio для Mac.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="7d1d1-105">Убедитесь, что [установлен Visual Studio для Mac](install-fsharp.md#install-f-with-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="7d1d1-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="7d1d1-106">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="7d1d1-106">Creating a console application</span></span>

<span data-ttu-id="7d1d1-107">Одним из самых основных проектов в Visual Studio для Mac является консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="7d1d1-108">Вот как это делается.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-108">Here's how to do it.</span></span>  <span data-ttu-id="7d1d1-109">После открытия Visual Studio для Mac:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="7d1d1-110">В меню **файл** укажите пункт **создать решение**.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="7d1d1-111">В диалоговом окне Новый проект есть два разных шаблона для консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="7d1d1-112">В другом > .NET, предназначенный для .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="7d1d1-113">Другой шаблон находится в приложении .NET Core — >, предназначенном для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="7d1d1-114">В этой статье должен работать один из шаблонов.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="7d1d1-115">В разделе консольное приложение C# при F# необходимости измените на.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="7d1d1-116">Нажмите кнопку **Далее** , чтобы перейти вперед.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="7d1d1-117">Присвойте проекту имя и выберите нужные параметры для приложения.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="7d1d1-118">Обратите внимание, что панель предварительного просмотра находится сбоку экрана, где отображается структура каталогов, которая будет создана на основе выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="7d1d1-119">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-119">Click **Create**.</span></span>  <span data-ttu-id="7d1d1-120">Теперь вы увидите F# проект в Обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="7d1d1-121">Написание кода</span><span class="sxs-lookup"><span data-stu-id="7d1d1-121">Writing your code</span></span>

<span data-ttu-id="7d1d1-122">Приступим к работе, сначала напишем некоторый код.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="7d1d1-123">Убедитесь, что файл `Program.fs` открыт, и замените его содержимое следующим:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="7d1d1-124">В предыдущем примере кода определена функция `square`, которая принимает входные данные с именем `x` и умножает ее на саму себя.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="7d1d1-125">Поскольку F# использует [вывод типа](../language-reference/type-inference.md), указывать тип `x` не нужно.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="7d1d1-126">F# Компилятор понимает типы, в которых умножение является допустимым, и присвоит тип `x` в зависимости от того, как вызывается `square`.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="7d1d1-127">При наведении указателя мыши на `square`вы должны увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-127">If you hover over `square`, you should see the following:</span></span>

```console
val square: x:int -> int
```

<span data-ttu-id="7d1d1-128">Это называется сигнатурой типа функции.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="7d1d1-129">Его можно прочитать следующим образом: "Square — это функция, которая принимает целое число с именем" x "и создает целое число".</span><span class="sxs-lookup"><span data-stu-id="7d1d1-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="7d1d1-130">Обратите внимание, что компилятор выдает `square` тип `int` для Now, так как умножение не является универсальным для *всех* типов, а является универсальным по отношению к закрытому набору типов.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="7d1d1-131">F# Компилятор выбрал `int` на этом этапе, но при вызове `square` с другим типом входных данных, например `float`, будет настроена сигнатура типа.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="7d1d1-132">Определена другая функция `main`, которая снабжена атрибутом `EntryPoint`, чтобы сообщить F# компилятору, что должно начаться выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="7d1d1-133">Он соответствует тому же соглашению, что и другие [языки программирования в стиле C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), где аргументы командной строки могут передаваться в эту функцию, и возвращается целочисленный код (обычно `0`).</span><span class="sxs-lookup"><span data-stu-id="7d1d1-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="7d1d1-134">Эта функция вызывает функцию `square` с аргументом `12`.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="7d1d1-135">Затем F# компилятор назначает тип `square` `int -> int` (то есть функция, которая принимает `int` и создает `int`).</span><span class="sxs-lookup"><span data-stu-id="7d1d1-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="7d1d1-136">Вызов `printfn` является отформатированной функцией печати, которая использует строку формата, аналогичную языку программирования в стиле C, параметры, соответствующие указанным в строке формата, а затем выводят результат и новую строку.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="7d1d1-137">Выполнение кода</span><span class="sxs-lookup"><span data-stu-id="7d1d1-137">Running your code</span></span>

<span data-ttu-id="7d1d1-138">Можно запустить код и просмотреть результаты, щелкнув **запустить** в меню верхнего уровня, а затем **запустить без отладки**.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="7d1d1-139">Это приведет к запуску программы без отладки и позволяет просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="7d1d1-140">Теперь в окне консоли, которое Visual Studio для Mac выводится на экран, должны отобразиться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="7d1d1-141">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="7d1d1-141">Congratulations!</span></span>  <span data-ttu-id="7d1d1-142">Вы создали первый F# проект в Visual Studio для Mac, записали F# функцию на печать результатов вызова этой функции и запустили проект, чтобы увидеть некоторые результаты.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="7d1d1-143">Использование F# интерактивного</span><span class="sxs-lookup"><span data-stu-id="7d1d1-143">Using F# Interactive</span></span>

<span data-ttu-id="7d1d1-144">Одной из лучших функций визуального F# инструментария в Visual Studio для Mac является F# интерактивное окно.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="7d1d1-145">Он позволяет отправить код в процесс, в котором можно вызвать этот код и просмотреть результат в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="7d1d1-146">Чтобы приступить к работе, выделите функцию `square`, определенную в коде.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="7d1d1-147">Затем в меню верхнего уровня щелкните **Edit (изменить** ).</span><span class="sxs-lookup"><span data-stu-id="7d1d1-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="7d1d1-148">Затем выберите **Отправить выделенный F# фрагмент в интерактивный**.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="7d1d1-149">Это приведет к выполнению кода в F# интерактивном окне.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="7d1d1-150">Кроме того, можно щелкнуть выделенный фрагмент правой кнопкой мыши и выбрать пункт **Отправить выделенное в F# интерактивное**окно.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="7d1d1-151">Вы должны увидеть F# интерактивное окно, в котором отображается следующее:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```console
>

val square : x:int -> int

>
```

<span data-ttu-id="7d1d1-152">Здесь показана та же сигнатура функции для функции `square`, которую вы видели ранее при наведении указателя мыши на функцию.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="7d1d1-153">Поскольку `square` теперь определен в F# интерактивном процессе, его можно вызвать с различными значениями:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="7d1d1-154">Эта функция выполняет функцию, привязывает результат к новому имени `it`и отображает тип и значение `it`.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="7d1d1-155">Обратите внимание, что каждая строка должна завершаться `;;`.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="7d1d1-156">Таким способом интерактивно известно о F# завершении вызова функции.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="7d1d1-157">Вы также можете определить новые функции в F# интерактивном режиме:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-157">You can also define new functions in F# Interactive:</span></span>

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="7d1d1-158">В приведенном выше примере определяется новая функция, `isOdd`, которая принимает `int` и проверяет, нечетна ли она!</span><span class="sxs-lookup"><span data-stu-id="7d1d1-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="7d1d1-159">Эту функцию можно вызвать, чтобы увидеть, что она возвращает с различными входными данными.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="7d1d1-160">Функции можно вызывать внутри вызовов функций:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-160">You can call functions within function calls:</span></span>

```console
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="7d1d1-161">Можно также использовать [оператор переадресации канала](../language-reference/symbol-and-operator-reference/index.md) для передачи значения в две функции:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="7d1d1-162">Оператор переадресации канала и многое другое рассматривается в последующих руководствах.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="7d1d1-163">Это лишь краткий обзор того, что можно сделать с F# помощью интерактивного.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="7d1d1-164">Дополнительные сведения см. в [интерактивном программировании F#с помощью ](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="7d1d1-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d1d1-165">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7d1d1-165">Next steps</span></span>

<span data-ttu-id="7d1d1-166">Если вы еще этого не сделали, ознакомьтесь с [обзором F# ](../tour.md), в котором рассматриваются некоторые основные функции F# языка.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="7d1d1-167">Вы получите общие сведения о некоторых F#возможностях и предоставьте достаточное количество примеров кода, которые вы можете скопировать в Visual Studio для Mac и выполнить.</span><span class="sxs-lookup"><span data-stu-id="7d1d1-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="7d1d1-168">Есть также некоторые отличные внешние ресурсы, которые можно использовать, выдемонстрируемые в этом [ F# руководством](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="7d1d1-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d1d1-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d1d1-169">See also</span></span>

- [<span data-ttu-id="7d1d1-170">F#программ</span><span class="sxs-lookup"><span data-stu-id="7d1d1-170">F# guide</span></span>](../index.yml)
- [<span data-ttu-id="7d1d1-171">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="7d1d1-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="7d1d1-172">F#Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="7d1d1-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="7d1d1-173">Определение типа</span><span class="sxs-lookup"><span data-stu-id="7d1d1-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="7d1d1-174">Справочник по символам и операторам</span><span class="sxs-lookup"><span data-stu-id="7d1d1-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
