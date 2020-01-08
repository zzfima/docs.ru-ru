---
title: Начало работы с F# Visual Studio
description: Узнайте, как использовать F# с Visual Studio.
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337350"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="8ab63-103">Начало работы с F# Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8ab63-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="8ab63-104">F#Визуальные F# средства поддерживаются в интегрированной среде разработки Visual Studio (IDE).</span><span class="sxs-lookup"><span data-stu-id="8ab63-104">F# and the Visual F# tooling are supported in the Visual Studio integrated development environment (IDE).</span></span>

<span data-ttu-id="8ab63-105">Для начала убедитесь, что у вас [установлена поддержка Visual Studio F# с поддержкой](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="8ab63-105">To begin, ensure that you have [Visual Studio installed with F# support](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="8ab63-106">Создание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="8ab63-106">Create a console application</span></span>

<span data-ttu-id="8ab63-107">Одним из самых основных проектов в Visual Studio является консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="8ab63-107">One of the most basic projects in Visual Studio is the console app.</span></span> <span data-ttu-id="8ab63-108">Вот как это сделать:</span><span class="sxs-lookup"><span data-stu-id="8ab63-108">Here's how to create one:</span></span>

1. <span data-ttu-id="8ab63-109">Запустите Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="8ab63-109">Open Visual Studio 2019.</span></span>

2. <span data-ttu-id="8ab63-110">На начальном экране выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="8ab63-110">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="8ab63-111">На странице **Создание нового проекта** выберите **F#** из списка язык.</span><span class="sxs-lookup"><span data-stu-id="8ab63-111">On the **Create a new project** page, choose **F#** from the Language list.</span></span>

4. <span data-ttu-id="8ab63-112">Выберите шаблон **консольное приложение (.NET Core)** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ab63-112">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

5. <span data-ttu-id="8ab63-113">На странице **Настройка нового проекта** введите имя в поле **имя проекта** .</span><span class="sxs-lookup"><span data-stu-id="8ab63-113">On the **Configure your new project** page, enter a name in the **Project name** box.</span></span> <span data-ttu-id="8ab63-114">Затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8ab63-114">Then, choose **Create**.</span></span>

   <span data-ttu-id="8ab63-115">Visual Studio создаст новый F# проект.</span><span class="sxs-lookup"><span data-stu-id="8ab63-115">Visual Studio creates the new F# project.</span></span> <span data-ttu-id="8ab63-116">Его можно увидеть в окне обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="8ab63-116">You can see it in the Solution Explorer window.</span></span>

## <a name="write-the-code"></a><span data-ttu-id="8ab63-117">Создание кода</span><span class="sxs-lookup"><span data-stu-id="8ab63-117">Write the code</span></span>

<span data-ttu-id="8ab63-118">Начнем с написания кода.</span><span class="sxs-lookup"><span data-stu-id="8ab63-118">Let's get started by writing some code.</span></span> <span data-ttu-id="8ab63-119">Убедитесь, что файл `Program.fs` открыт, и замените его содержимое следующим:</span><span class="sxs-lookup"><span data-stu-id="8ab63-119">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="8ab63-120">Предыдущий пример кода определяет функцию с именем `square`, которая принимает входные данные с именем `x` и умножает ее на саму себя.</span><span class="sxs-lookup"><span data-stu-id="8ab63-120">The previous code sample defines a function called `square` that takes an input named `x` and multiplies it by itself.</span></span> <span data-ttu-id="8ab63-121">Поскольку F# использует [вывод типа](../language-reference/type-inference.md), указывать тип `x` не нужно.</span><span class="sxs-lookup"><span data-stu-id="8ab63-121">Because F# uses [Type inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span> <span data-ttu-id="8ab63-122">F# Компилятор понимает типы, в которых умножение является допустимым, и назначает тип для `x` в зависимости от способа вызова `square`.</span><span class="sxs-lookup"><span data-stu-id="8ab63-122">The F# compiler understands the types where multiplication is valid and assigns a type to `x` based on how `square` is called.</span></span> <span data-ttu-id="8ab63-123">При наведении указателя мыши на `square`вы должны увидеть следующее:</span><span class="sxs-lookup"><span data-stu-id="8ab63-123">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="8ab63-124">Это называется сигнатурой типа функции.</span><span class="sxs-lookup"><span data-stu-id="8ab63-124">This is what is known as the function's type signature.</span></span> <span data-ttu-id="8ab63-125">Его можно прочитать следующим образом: "Square — это функция, которая принимает целое число с именем" x "и создает целое число".</span><span class="sxs-lookup"><span data-stu-id="8ab63-125">It can be read like this: "Square is a function that takes an integer named x and produces an integer".</span></span> <span data-ttu-id="8ab63-126">Компилятор предоставил `square` тип `int` для Now; Это связано с тем, что умножение не является универсальным для *всех* типов, а вместо закрытого набора типов.</span><span class="sxs-lookup"><span data-stu-id="8ab63-126">The compiler gave `square` the `int` type for now; this is because multiplication is not generic across *all* types but rather a closed set of types.</span></span> <span data-ttu-id="8ab63-127">F# Компилятор будет корректировать сигнатуру типа при вызове `square` с другим типом входных данных, например `float`.</span><span class="sxs-lookup"><span data-stu-id="8ab63-127">The F# compiler will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="8ab63-128">Определена другая функция `main`, которая снабжена атрибутом `EntryPoint`.</span><span class="sxs-lookup"><span data-stu-id="8ab63-128">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute.</span></span> <span data-ttu-id="8ab63-129">Этот атрибут сообщает F# компилятору, что должно начаться выполнение программы.</span><span class="sxs-lookup"><span data-stu-id="8ab63-129">This attribute tells the F# compiler that program execution should start there.</span></span> <span data-ttu-id="8ab63-130">Он соответствует тому же соглашению, что и другие [языки программирования в стиле C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), где аргументы командной строки могут передаваться в эту функцию, и возвращается целочисленный код (обычно `0`).</span><span class="sxs-lookup"><span data-stu-id="8ab63-130">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="8ab63-131">Он находится в функции точки входа `main`, что вызывается функция `square` с аргументом `12`.</span><span class="sxs-lookup"><span data-stu-id="8ab63-131">It is in the entry point function, `main`, that you call the `square` function with an argument of `12`.</span></span> <span data-ttu-id="8ab63-132">Затем F# компилятор назначает тип `square` `int -> int` (то есть функция, которая принимает `int` и создает `int`).</span><span class="sxs-lookup"><span data-stu-id="8ab63-132">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function that takes an `int` and produces an `int`).</span></span> <span data-ttu-id="8ab63-133">Вызов `printfn` является отформатированной функцией печати, которая использует строку формата и выводит результат (и новую строку).</span><span class="sxs-lookup"><span data-stu-id="8ab63-133">The call to `printfn` is a formatted printing function that uses a format string and prints the result (and a new line).</span></span> <span data-ttu-id="8ab63-134">Строка формата, аналогичная языку программирования в стиле C, имеет параметры (`%d`), соответствующие переданным в него аргументам, в данном случае `12` и `(square 12)`.</span><span class="sxs-lookup"><span data-stu-id="8ab63-134">The format string, similar to C-style programming languages, has parameters (`%d`) that correspond to the arguments that are passed to it, in this case, `12` and `(square 12)`.</span></span>

## <a name="run-the-code"></a><span data-ttu-id="8ab63-135">Выполнение кода</span><span class="sxs-lookup"><span data-stu-id="8ab63-135">Run the code</span></span>

<span data-ttu-id="8ab63-136">Можно выполнить код и просмотреть результаты, нажав клавиши **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="8ab63-136">You can run the code and see the results by pressing **Ctrl**+**F5**.</span></span> <span data-ttu-id="8ab63-137">Кроме того, можно выбрать **отладку** > **Запуск без отладки** из строки меню верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="8ab63-137">Alternatively, you can choose the **Debug** > **Start Without Debugging** from the top-level menu bar.</span></span> <span data-ttu-id="8ab63-138">При этом запускается программа без отладки.</span><span class="sxs-lookup"><span data-stu-id="8ab63-138">This runs the program without debugging.</span></span>

<span data-ttu-id="8ab63-139">Следующие выходные данные выводятся в окне консоли, которое открыл Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="8ab63-139">The following output prints to the console window that Visual Studio opened:</span></span>

```console
12 squared is: 144!
```

<span data-ttu-id="8ab63-140">Поздравляем!</span><span class="sxs-lookup"><span data-stu-id="8ab63-140">Congratulations!</span></span> <span data-ttu-id="8ab63-141">Вы создали первый F# проект в Visual Studio, написали F# функцию, которая вычисляет и выводит значение, и запускает проект для просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="8ab63-141">You've created your first F# project in Visual Studio, written an F# function that calculates and prints a value, and run the project to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ab63-142">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="8ab63-142">Next steps</span></span>

<span data-ttu-id="8ab63-143">Если вы еще этого не сделали, ознакомьтесь с [обзором F# ](../tour.md), в котором рассматриваются некоторые основные функции F# языка.</span><span class="sxs-lookup"><span data-stu-id="8ab63-143">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span> <span data-ttu-id="8ab63-144">В нем представлен обзор некоторых возможностей F# и объемных примеров кода, которые можно скопировать в Visual Studio и выполнить.</span><span class="sxs-lookup"><span data-stu-id="8ab63-144">It provides an overview of some of the capabilities of F# and ample code samples that you can copy into Visual Studio and run.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8ab63-145">Обзор языка F#</span><span class="sxs-lookup"><span data-stu-id="8ab63-145">Tour of F#</span></span>](../tour.md)

## <a name="see-also"></a><span data-ttu-id="8ab63-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ab63-146">See also</span></span>

- [<span data-ttu-id="8ab63-147">F#Справочник по языку</span><span class="sxs-lookup"><span data-stu-id="8ab63-147">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="8ab63-148">Определение типа</span><span class="sxs-lookup"><span data-stu-id="8ab63-148">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="8ab63-149">Справочник по символам и операторам</span><span class="sxs-lookup"><span data-stu-id="8ab63-149">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
