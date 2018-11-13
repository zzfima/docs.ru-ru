---
title: Начало работы с F# в Visual Studio
description: Сведения об использовании F# с помощью Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 3dac8466501338873aeb308ceac9274a7934a8a9
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "43872855"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="4d257-103">Начало работы с F# в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d257-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="4d257-104">F# и инструментария Visual F# поддерживаются в Интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4d257-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="4d257-105">Чтобы начать, убедитесь, что у вас есть [Visual Studio, установленной с помощью F#](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="4d257-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="4d257-106">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="4d257-106">Creating a console application</span></span>

<span data-ttu-id="4d257-107">Одним из основных проектов в Visual Studio — это консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="4d257-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="4d257-108">Вот как это делается.</span><span class="sxs-lookup"><span data-stu-id="4d257-108">Here's how to do it.</span></span>  <span data-ttu-id="4d257-109">После открытия Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="4d257-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="4d257-110">На **файл** последовательно выберите пункты **New**, а затем выберите **проекта**.</span><span class="sxs-lookup"><span data-stu-id="4d257-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="4d257-111">В New Project диалоговое окно, в разделе **шаблоны**, вы должны увидеть **Visual F#**.</span><span class="sxs-lookup"><span data-stu-id="4d257-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="4d257-112">Выберите, чтобы отобразить шаблоны F#.</span><span class="sxs-lookup"><span data-stu-id="4d257-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="4d257-113">Выберите либо **.NET Core, консольное приложение** или **консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="4d257-113">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="4d257-114">Выберите **хорошо** кнопку, чтобы создать проект F#!</span><span class="sxs-lookup"><span data-stu-id="4d257-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="4d257-115">Теперь вы увидите проекта F# в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="4d257-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="4d257-116">Написание кода</span><span class="sxs-lookup"><span data-stu-id="4d257-116">Writing your code</span></span>

<span data-ttu-id="4d257-117">Давайте начнем сначала пишет некоторый код.</span><span class="sxs-lookup"><span data-stu-id="4d257-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="4d257-118">Убедитесь, что `Program.fs` файл открыт и замените его содержимое следующим:</span><span class="sxs-lookup"><span data-stu-id="4d257-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="4d257-119">В предыдущем примере кода, функция `square` был определен который принимает ввод с именем `x` и умножает его самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="4d257-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="4d257-120">Так как F# использует [вывод типа](../language-reference/type-inference.md), тип `x` не должны быть указаны.</span><span class="sxs-lookup"><span data-stu-id="4d257-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="4d257-121">Компилятор F# понимает типы, где умножение является допустимым и будет назначать тип для `x` зависит `square` вызывается.</span><span class="sxs-lookup"><span data-stu-id="4d257-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="4d257-122">Если навести `square`, вы должны увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="4d257-122">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="4d257-123">Это связано с так называемой сигнатура типа функции.</span><span class="sxs-lookup"><span data-stu-id="4d257-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="4d257-124">Может быть прочитан следующим образом: «квадрата является функция, которая принимает целое число с именем x и создает целое число».</span><span class="sxs-lookup"><span data-stu-id="4d257-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="4d257-125">Обратите внимание, что компилятор обеспечивал `square` `int` тип сейчас - это обусловлено умножения, не является универсальным через *все* типы, но довольно универсален через набор закрытых типов.</span><span class="sxs-lookup"><span data-stu-id="4d257-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="4d257-126">Компилятор F# выбраны `int` это точка, но он настроит сигнатуре типа при вызове метода `square` с другим ввода типа, например `float`.</span><span class="sxs-lookup"><span data-stu-id="4d257-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="4d257-127">Другую функцию `main`, определяется, который дополняется `EntryPoint` атрибут для указания компилятору F#, выполнение программы следует начать с этого.</span><span class="sxs-lookup"><span data-stu-id="4d257-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="4d257-128">Его следует тому же образцу что и другие [языков программирования в стиле C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), где эту функцию можно передать аргументы командной строки и возвращается код целого числа (обычно `0`).</span><span class="sxs-lookup"><span data-stu-id="4d257-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="4d257-129">В этой функции, мы вызываем `square` функцию с аргументом `12`.</span><span class="sxs-lookup"><span data-stu-id="4d257-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="4d257-130">Компилятор F# затем назначает тип `square` быть `int -> int` (то есть функция, которая принимает `int` и создает `int`).</span><span class="sxs-lookup"><span data-stu-id="4d257-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="4d257-131">Вызов `printfn` является форматированный печати функция, которая использует строку формата, аналогичную языков программирования C-стиля, параметры, которые соответствуют заданным в строке формата, а затем распечатывает результат и новую строку.</span><span class="sxs-lookup"><span data-stu-id="4d257-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="4d257-132">Выполнение кода</span><span class="sxs-lookup"><span data-stu-id="4d257-132">Running your code</span></span>

<span data-ttu-id="4d257-133">Можно выполнить код и увидеть результаты, нажав клавишу **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="4d257-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="4d257-134">Это запускает программу без отладки и дает возможность видеть результаты.</span><span class="sxs-lookup"><span data-stu-id="4d257-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="4d257-135">Кроме того, вы можете **Отладка** меню верхнего уровня элемент в Visual Studio, выбрав **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="4d257-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="4d257-136">Теперь вы увидите напечатаны в окне консоли, Visual Studio появилось следующее:</span><span class="sxs-lookup"><span data-stu-id="4d257-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="4d257-137">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="4d257-137">Congratulations!</span></span>  <span data-ttu-id="4d257-138">Вы создали первый проект F# в Visual Studio, написаны функция F#, распечатать результаты вызова этой функции и запустите проект, чтобы увидеть некоторые результаты.</span><span class="sxs-lookup"><span data-stu-id="4d257-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d257-139">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4d257-139">Next steps</span></span>

<span data-ttu-id="4d257-140">Если это еще не сделано, см. статью [обзор языка F#](../tour.md), где приведены некоторые основные возможности языка F#.</span><span class="sxs-lookup"><span data-stu-id="4d257-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="4d257-141">Он будет дам обзор некоторых возможностей языка F# и предоставляет примеры кода можно в полной мере, можно скопировать в Visual Studio и запустить.</span><span class="sxs-lookup"><span data-stu-id="4d257-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="4d257-142">Существуют также некоторые полезные внешние ресурсы, которые можно использовать, показывавшие в [руководство по F#](../index.md).</span><span class="sxs-lookup"><span data-stu-id="4d257-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d257-143">См. также</span><span class="sxs-lookup"><span data-stu-id="4d257-143">See also</span></span>

- [<span data-ttu-id="4d257-144">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="4d257-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="4d257-145">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="4d257-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="4d257-146">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="4d257-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="4d257-147">Справочник символов и оператор</span><span class="sxs-lookup"><span data-stu-id="4d257-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
