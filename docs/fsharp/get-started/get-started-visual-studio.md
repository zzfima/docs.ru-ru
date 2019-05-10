---
title: Начало работы с F# в Visual Studio
description: Сведения об использовании F# с помощью Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 9b02a5d295f982b1911dab567213fa9a2b6c4304
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754863"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="6e768-103">Начало работы с F# в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6e768-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="6e768-104">F#и визуальный F# инструментарий поддерживаются в Интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6e768-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="6e768-105">Чтобы начать, убедитесь, что у вас есть [установлена среда Visual Studio с F# ](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="6e768-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="6e768-106">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="6e768-106">Creating a console application</span></span>

<span data-ttu-id="6e768-107">Одним из основных проектов в Visual Studio — это консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="6e768-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="6e768-108">Вот как это делается.</span><span class="sxs-lookup"><span data-stu-id="6e768-108">Here's how to do it.</span></span>  <span data-ttu-id="6e768-109">После открытия Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="6e768-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="6e768-110">На **файл** последовательно выберите пункты **New**, а затем выберите **проекта**.</span><span class="sxs-lookup"><span data-stu-id="6e768-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="6e768-111">В New Project диалоговое окно, в разделе **шаблоны**, вы должны увидеть **Visual F#** .</span><span class="sxs-lookup"><span data-stu-id="6e768-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="6e768-112">Выберите для отображения F# шаблонов.</span><span class="sxs-lookup"><span data-stu-id="6e768-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="6e768-113">Выберите либо **.NET Core, консольное приложение** или **консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="6e768-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="6e768-114">Выберите **хорошо** кнопку, чтобы создать F# проекта!</span><span class="sxs-lookup"><span data-stu-id="6e768-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="6e768-115">Теперь вы увидите F# проекта в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="6e768-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="6e768-116">Написание кода</span><span class="sxs-lookup"><span data-stu-id="6e768-116">Writing your code</span></span>

<span data-ttu-id="6e768-117">Давайте начнем сначала пишет некоторый код.</span><span class="sxs-lookup"><span data-stu-id="6e768-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="6e768-118">Убедитесь, что `Program.fs` файл открыт и замените его содержимое следующим:</span><span class="sxs-lookup"><span data-stu-id="6e768-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="6e768-119">В предыдущем примере кода, функция `square` был определен который принимает ввод с именем `x` и умножает его самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="6e768-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="6e768-120">Так как F# использует [вывод типа](../language-reference/type-inference.md), тип `x` не должны быть указаны.</span><span class="sxs-lookup"><span data-stu-id="6e768-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="6e768-121">F# Компилятор распознает типы, где умножение является допустимым, а также будет назначать тип для `x` зависит `square` вызывается.</span><span class="sxs-lookup"><span data-stu-id="6e768-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="6e768-122">Если навести `square`, вы должны увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="6e768-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="6e768-123">Это связано с так называемой сигнатура типа функции.</span><span class="sxs-lookup"><span data-stu-id="6e768-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="6e768-124">Может быть прочитан следующим образом: «Квадрата является функция, которая принимает целое число с именем x и создает целое число».</span><span class="sxs-lookup"><span data-stu-id="6e768-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="6e768-125">Обратите внимание, что компилятор обеспечивал `square` `int` тип сейчас - это обусловлено умножения, не является универсальным через *все* типы, но довольно универсален через набор закрытых типов.</span><span class="sxs-lookup"><span data-stu-id="6e768-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="6e768-126">F# Компилятора выбраны `int` это точка, но он настроит сигнатуре типа при вызове метода `square` с другим ввода типа, например `float`.</span><span class="sxs-lookup"><span data-stu-id="6e768-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="6e768-127">Другую функцию, `main`, определяется, который дополняется `EntryPoint` атрибут, чтобы сообщить F# компилятора, выполнение программы следует начать с этого.</span><span class="sxs-lookup"><span data-stu-id="6e768-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="6e768-128">Его следует тому же образцу что и другие [языков программирования в стиле C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), где эту функцию можно передать аргументы командной строки и возвращается код целого числа (обычно `0`).</span><span class="sxs-lookup"><span data-stu-id="6e768-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="6e768-129">В этой функции, мы вызываем `square` функцию с аргументом `12`.</span><span class="sxs-lookup"><span data-stu-id="6e768-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="6e768-130">F# Компилятор затем назначает тип `square` быть `int -> int` (то есть функция, которая принимает `int` и создает `int`).</span><span class="sxs-lookup"><span data-stu-id="6e768-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="6e768-131">Вызов `printfn` является форматированный печати функция, которая использует строку формата, аналогичную языков программирования C-стиля, параметры, которые соответствуют заданным в строке формата, а затем распечатывает результат и новую строку.</span><span class="sxs-lookup"><span data-stu-id="6e768-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="6e768-132">Выполнение кода</span><span class="sxs-lookup"><span data-stu-id="6e768-132">Running your code</span></span>

<span data-ttu-id="6e768-133">Можно выполнить код и увидеть результаты, нажав клавишу **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="6e768-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="6e768-134">Это запускает программу без отладки и дает возможность видеть результаты.</span><span class="sxs-lookup"><span data-stu-id="6e768-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="6e768-135">Кроме того, вы можете **Отладка** меню верхнего уровня элемент в Visual Studio, выбрав **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="6e768-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="6e768-136">Теперь вы увидите напечатаны в окне консоли, Visual Studio появилось следующее:</span><span class="sxs-lookup"><span data-stu-id="6e768-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="6e768-137">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="6e768-137">Congratulations!</span></span>  <span data-ttu-id="6e768-138">Вы создали свое первое F# проект в Visual Studio, написанные F# функция печати результаты вызова метода, функции и запустите проект, чтобы увидеть некоторые результаты.</span><span class="sxs-lookup"><span data-stu-id="6e768-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6e768-139">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6e768-139">Next steps</span></span>

<span data-ttu-id="6e768-140">Если это еще не сделано, см. статью [примером F# ](../tour.md), где приведены некоторые основные функции F# языка.</span><span class="sxs-lookup"><span data-stu-id="6e768-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="6e768-141">Она даст вам Общие сведения о некоторых возможностях F#и приводятся примеры кода можно в полной мере, которые можно скопировать в Visual Studio и запустить.</span><span class="sxs-lookup"><span data-stu-id="6e768-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="6e768-142">Существуют также некоторые полезные внешние ресурсы, которые можно использовать, показывавшие в [ F# руководство](../index.md).</span><span class="sxs-lookup"><span data-stu-id="6e768-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e768-143">См. также</span><span class="sxs-lookup"><span data-stu-id="6e768-143">See also</span></span>

- [<span data-ttu-id="6e768-144">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="6e768-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="6e768-145">F#Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="6e768-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="6e768-146">Вывод типа</span><span class="sxs-lookup"><span data-stu-id="6e768-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="6e768-147">Справочник символов и оператор</span><span class="sxs-lookup"><span data-stu-id="6e768-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
