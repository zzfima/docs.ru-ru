---
title: Начало работы с F# Visual Studio
description: Узнайте, как использовать F# с Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: e573af67a1fc00b0a340f8c73ab1ee0ed2b97810
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082696"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="7ccf7-103">Начало работы с F# Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7ccf7-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="7ccf7-104">F#и визуальные F# средства поддерживаются в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="7ccf7-105">Для начала убедитесь, что у вас [установлена Visual Studio с F# ](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="7ccf7-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="7ccf7-106">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="7ccf7-106">Creating a console application</span></span>

<span data-ttu-id="7ccf7-107">Одним из самых основных проектов в Visual Studio является консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="7ccf7-108">Вот как это делается.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-108">Here's how to do it.</span></span>  <span data-ttu-id="7ccf7-109">После открытия Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="7ccf7-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="7ccf7-110">В меню **файл** наведите указатель мыши на пункт **создать**и выберите **проект**.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="7ccf7-111">В диалоговом окне Новый проект в разделе **шаблоны**отобразится **визуальный F#** элемент.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="7ccf7-112">Выберите этот параметр F# , чтобы отобразить шаблоны.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="7ccf7-113">Выберите **консольное приложение .NET Core** или **консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-113">Select either **.NET Core Console app** or **Console app**.</span></span>

4. <span data-ttu-id="7ccf7-114">Нажмите кнопку **ОК** , чтобы создать F# проект.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="7ccf7-115">Теперь вы увидите F# проект в Обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="7ccf7-116">Написание кода</span><span class="sxs-lookup"><span data-stu-id="7ccf7-116">Writing your code</span></span>

<span data-ttu-id="7ccf7-117">Приступим к работе, сначала напишем некоторый код.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="7ccf7-118">Убедитесь, что `Program.fs` файл открыт, и замените его содержимое следующим:</span><span class="sxs-lookup"><span data-stu-id="7ccf7-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="7ccf7-119">В предыдущем примере кода определена функция `square` , которая принимает входные данные с именем `x` и умножает ее на саму себя.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="7ccf7-120">Поскольку F# использует [вывод типа](../language-reference/type-inference.md), тип `x` не требуется указывать.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="7ccf7-121">F# Компилятор понимает типы, в которых умножение является допустимым, и присвоит тип в `x` зависимости от того, `square` как вызывается.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="7ccf7-122">Если навести указатель `square`мыши на, вы увидите следующее:</span><span class="sxs-lookup"><span data-stu-id="7ccf7-122">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="7ccf7-123">Это называется сигнатурой типа функции.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="7ccf7-124">Его можно прочитать следующим образом: "Square — это функция, которая принимает целое число с именем x и создает целое число".</span><span class="sxs-lookup"><span data-stu-id="7ccf7-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="7ccf7-125">Обратите внимание, что `square` компилятор `int` выдавал тип для Now, так как умножение не является универсальным для *всех* типов, а является универсальным по отношению к закрытому набору типов.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="7ccf7-126">`square` Компилятор выбрал на этом этапе, но при вызове с `float`другим типом входных данных, например, он будет корректировать сигнатуру типа. `int` F#</span><span class="sxs-lookup"><span data-stu-id="7ccf7-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="7ccf7-127">Определена другая `main`функция,, которая снабжена `EntryPoint` атрибутом, чтобы сообщить F# компилятору, что должно начаться выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="7ccf7-128">Он соответствует тому же соглашению, что и другие [языки программирования в стиле C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), где аргументы командной строки могут передаваться в эту функцию, и возвращается целочисленный код `0`(обычно).</span><span class="sxs-lookup"><span data-stu-id="7ccf7-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="7ccf7-129">В этой функции мы вызываем `square` функцию с `12`аргументом.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="7ccf7-130">Затем F# компилятор `square` присваивает тип `int -> int` (т. е. функции, которая принимает `int` и создает объект `int`).</span><span class="sxs-lookup"><span data-stu-id="7ccf7-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="7ccf7-131">Вызов `printfn` — это форматированная функция печати, которая использует строку форматирования, аналогичную языку программирования в стиле C, параметры, соответствующие указанным в строке формата, а затем выводят результат и новую строку.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="7ccf7-132">Выполнение кода</span><span class="sxs-lookup"><span data-stu-id="7ccf7-132">Running your code</span></span>

<span data-ttu-id="7ccf7-133">Вы можете запустить код и просмотреть результаты, нажав клавиши **CTRL**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="7ccf7-134">Это запускает программу без отладки и позволяет просматривать результаты.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="7ccf7-135">Кроме того, можно выбрать пункт **Отладка** пункта меню верхнего уровня в Visual Studio и выбрать **Запуск без отладки**.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="7ccf7-136">Теперь в окне консоли, которое было извлечено Visual Studio, должны отобразиться следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="7ccf7-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="7ccf7-137">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="7ccf7-137">Congratulations!</span></span>  <span data-ttu-id="7ccf7-138">Вы создали первый F# проект в Visual Studio, записали F# функцию на печать результатов вызова этой функции и запустили проект, чтобы увидеть некоторые результаты.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ccf7-139">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7ccf7-139">Next steps</span></span>

<span data-ttu-id="7ccf7-140">Если вы еще этого не сделали, ознакомьтесь с [обзором F# ](../tour.md), в котором рассматриваются некоторые основные функции F# языка.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="7ccf7-141">Он предоставляет обзор некоторых возможностей F#и предоставляет примеры кода, которые можно скопировать в Visual Studio и выполнить.</span><span class="sxs-lookup"><span data-stu-id="7ccf7-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="7ccf7-142">Есть также некоторые отличные внешние ресурсы, которые можно использовать, выдемонстрируемые в этом [ F# руководством](../index.md).</span><span class="sxs-lookup"><span data-stu-id="7ccf7-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7ccf7-143">См. также</span><span class="sxs-lookup"><span data-stu-id="7ccf7-143">See also</span></span>

- [<span data-ttu-id="7ccf7-144">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="7ccf7-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="7ccf7-145">F#Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="7ccf7-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="7ccf7-146">Определение типа</span><span class="sxs-lookup"><span data-stu-id="7ccf7-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="7ccf7-147">Справочник по символам и операторам</span><span class="sxs-lookup"><span data-stu-id="7ccf7-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
