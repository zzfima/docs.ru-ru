---
title: Main() и аргументы командной строки (Руководство по программированию на C#)
ms.date: 08/02/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 75610174fdc91e4a29f17dc5563a7298c56a44e2
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="845fd-102">Main() и аргументы командной строки (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="845fd-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="845fd-103">Метод `Main` — это точка входа приложения C#.</span><span class="sxs-lookup"><span data-stu-id="845fd-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="845fd-104">(Библиотекам и службам точка входа в виде метода `Main` не требуется.) Когда приложение запускается, первым вызывается именно метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="845fd-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="845fd-105">В программе на C# может существовать только одна точка входа.</span><span class="sxs-lookup"><span data-stu-id="845fd-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="845fd-106">Если у вас есть несколько классов с методом `Main`, программу нужно компилировать с параметром **/main**, чтобы указать, какой из методов `Main` будет использоваться в качестве точки входа.</span><span class="sxs-lookup"><span data-stu-id="845fd-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="845fd-107">Дополнительные сведения см. в разделе [/main (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="845fd-107">For more information, see [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span></span>

 [!code-csharp[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]

## <a name="overview"></a><span data-ttu-id="845fd-108">Обзор</span><span class="sxs-lookup"><span data-stu-id="845fd-108">Overview</span></span>

- <span data-ttu-id="845fd-109">Метод `Main` — это точка входа для выполняемой программы. Это начальный и завершающий этапы управления программой.</span><span class="sxs-lookup"><span data-stu-id="845fd-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="845fd-110">`Main` объявляется внутри класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="845fd-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="845fd-111">Метод `Main` должен быть [статическим](../../../csharp/language-reference/keywords/static.md). Он может не быть [открытым](../../../csharp/language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="845fd-111">`Main` must be [static](../../../csharp/language-reference/keywords/static.md) and it need not be [public](../../../csharp/language-reference/keywords/public.md).</span></span> <span data-ttu-id="845fd-112">(В предыдущем примере он по умолчанию получает уровень доступа [private](../../../csharp/language-reference/keywords/private.md) (закрытый).) Класс или структура, в которой он объявлен, не обязаны быть статическими.</span><span class="sxs-lookup"><span data-stu-id="845fd-112">(In the earlier example, it receives the default access of [private](../../../csharp/language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="845fd-113">Метод `Main` может иметь значение `void`, `int` или (начиная с C# 7.1) `Task`, а также тип возвращаемого значения `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="845fd-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="845fd-114">Если только `Main` возвращает `Task` или `Task<int>`, объявление `Main` может включать модификатор [`async`](../../language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="845fd-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="845fd-115">Обратите внимание, что это, в частности, исключает метод `async void Main`.</span><span class="sxs-lookup"><span data-stu-id="845fd-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="845fd-116">Метод `Main` может быть объявлен с параметром `string[]`, который содержит аргументы командной строки, или без него.</span><span class="sxs-lookup"><span data-stu-id="845fd-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="845fd-117">Когда вы используете Visual Studio для создания Windows-приложений, вы можете добавить параметр вручную либо воспользоваться классом <xref:System.Environment>, чтобы получить аргументы командной строки.</span><span class="sxs-lookup"><span data-stu-id="845fd-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment> class to obtain the command-line arguments.</span></span> <span data-ttu-id="845fd-118">Параметры считываются как аргументы командной строки, индексы которых начинаются с нуля.</span><span class="sxs-lookup"><span data-stu-id="845fd-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="845fd-119">В отличие от C и C++, имя программы не рассматривается как первый аргумент командной строки.</span><span class="sxs-lookup"><span data-stu-id="845fd-119">Unlike C and C++, the name of the program is not treated as the first command-line argument.</span></span>

<span data-ttu-id="845fd-120">Добавление значений `async` и `Task`, а также типов возвращаемого значения `Task<int>` упрощает код программы, когда консольным приложениям требуется запустить и ожидать (`await`) асинхронные операции в `Main`.</span><span class="sxs-lookup"><span data-stu-id="845fd-120">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="845fd-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="845fd-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="845fd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="845fd-122">See also</span></span>
[<span data-ttu-id="845fd-123">Сборка из командной строки с помощью csc.exe</span><span class="sxs-lookup"><span data-stu-id="845fd-123">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
[<span data-ttu-id="845fd-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="845fd-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="845fd-125">Методы</span><span class="sxs-lookup"><span data-stu-id="845fd-125">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
[<span data-ttu-id="845fd-126">Структура программы C#</span><span class="sxs-lookup"><span data-stu-id="845fd-126">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
