---
title: '#Справочник по C#. Директива препроцессора if'
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: d047b88f202341a795834809d0b601706c30fcb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75899856"
---
# <a name="if-c-reference"></a><span data-ttu-id="849dd-102">Справочник по C#. #if</span><span class="sxs-lookup"><span data-stu-id="849dd-102">#if (C# reference)</span></span>

<span data-ttu-id="849dd-103">Когда компилятор C# встречает директиву `#if`, за которой следует директива [#endif](preprocessor-endif.md), код между этими директивами он компилирует, только когда определен указанный символ.</span><span class="sxs-lookup"><span data-stu-id="849dd-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="849dd-104">В отличие от С и С++ здесь нельзя назначить символу числовое значение.</span><span class="sxs-lookup"><span data-stu-id="849dd-104">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="849dd-105">Оператор `#if` в C# является логическим. Он проверяет только одно условие — определен ли указанный символ.</span><span class="sxs-lookup"><span data-stu-id="849dd-105">The `#if` statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="849dd-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="849dd-106">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="849dd-107">Операторы [==](../operators/equality-operators.md#equality-operator-) (равенство) и [!=](../operators/equality-operators.md#inequality-operator-) (неравенство) можно использовать только для проверки значений [bool](../builtin-types/bool.md)`true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="849dd-107">You can use the operators [==](../operators/equality-operators.md#equality-operator-) (equality) and [!=](../operators/equality-operators.md#inequality-operator-) (inequality) only to test for the [bool](../builtin-types/bool.md) values `true` or `false`.</span></span> <span data-ttu-id="849dd-108">Значение `true` означает, что символ определен.</span><span class="sxs-lookup"><span data-stu-id="849dd-108">`true` means the symbol is defined.</span></span> <span data-ttu-id="849dd-109">Инструкция `#if DEBUG` имеет то же значение, что и `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="849dd-109">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="849dd-110">Вы можете использовать операторы [&& (и)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (или)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) и [! (не)](../operators/boolean-logical-operators.md#logical-negation-operator-), чтобы узнать, определено ли несколько символов.</span><span class="sxs-lookup"><span data-stu-id="849dd-110">You can use the [&& (and)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (or)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-), and [! (not)](../operators/boolean-logical-operators.md#logical-negation-operator-) operators to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="849dd-111">Можно также группировать символы и операторы при помощи скобок.</span><span class="sxs-lookup"><span data-stu-id="849dd-111">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="849dd-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="849dd-112">Remarks</span></span>

<span data-ttu-id="849dd-113">`#if`, как и директивы [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) и [#undef](preprocessor-undef.md), позволяет включить или исключить код в зависимости от существования одного или нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="849dd-113">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="849dd-114">Это может быть полезно при компиляции кода для отладки или для определенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="849dd-114">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="849dd-115">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="849dd-115">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="849dd-116">`#define` позволяет определить символ,</span><span class="sxs-lookup"><span data-stu-id="849dd-116">`#define` lets you define a symbol.</span></span> <span data-ttu-id="849dd-117">чтобы директива `#if`, которой передается этот символ, возвращала значение `true`.</span><span class="sxs-lookup"><span data-stu-id="849dd-117">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="849dd-118">Также символ можно определить с помощью параметра компилятора [-define](../compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="849dd-118">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="849dd-119">Для отмены определения символа служит директива [#undef](preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="849dd-119">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="849dd-120">Символ, определенный с помощью `-define` или `#define`, не конфликтует с одноименной переменной.</span><span class="sxs-lookup"><span data-stu-id="849dd-120">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="849dd-121">Соответственно, имя переменной не должно передаваться директиве препроцессора, а символ может использоваться только в директиве препроцессора.</span><span class="sxs-lookup"><span data-stu-id="849dd-121">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="849dd-122">Символ, создаваемый с помощью `#define`, будет определен в пределах того файл, в котором он определен.</span><span class="sxs-lookup"><span data-stu-id="849dd-122">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="849dd-123">Система сборки также учитывает символы препроцессора, представляющие [целевые платформы](../../../standard/frameworks.md) в проектах в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="849dd-123">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md) in SDK-style projects.</span></span> <span data-ttu-id="849dd-124">Они полезны при создании приложений, предназначенных для нескольких реализаций или версий .NET.</span><span class="sxs-lookup"><span data-stu-id="849dd-124">They're useful when creating applications that can target more than one .NET implementation or version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> <span data-ttu-id="849dd-125">Для традиционных проектов .NET Framework необходимо вручную настроить символы условной компиляции для различных целевых платформ в Visual Studio с помощью страниц свойств проекта.</span><span class="sxs-lookup"><span data-stu-id="849dd-125">For traditional .NET Framework projects, you have to manually configure the conditional compilation symbols for the different target frameworks in Visual Studio via the project's properties pages.</span></span>

<span data-ttu-id="849dd-126">Другие предопределенные символы включают константы DEBUG и TRACE.</span><span class="sxs-lookup"><span data-stu-id="849dd-126">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="849dd-127">Вы можете переопределить значения для проектов с помощью `#define`.</span><span class="sxs-lookup"><span data-stu-id="849dd-127">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="849dd-128">Например, символ DEBUG автоматически устанавливается в зависимости от свойств конфигурации сборки (в режиме отладки или выпуска).</span><span class="sxs-lookup"><span data-stu-id="849dd-128">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="849dd-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="849dd-129">Examples</span></span>

<span data-ttu-id="849dd-130">В следующем примере показано, как определить символ MYTEST в файле и затем протестировать значения символов MYTEST и DEBUG.</span><span class="sxs-lookup"><span data-stu-id="849dd-130">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="849dd-131">Выходные данные этого примера зависят от режима конфигурации, в котором создан проект (режим отладки или выпуска).</span><span class="sxs-lookup"><span data-stu-id="849dd-131">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

```csharp
#define MYTEST
using System;
public class MyClass
{
    static void Main()
    {
#if (DEBUG && !MYTEST)
        Console.WriteLine("DEBUG is defined");
#elif (!DEBUG && MYTEST)
        Console.WriteLine("MYTEST is defined");
#elif (DEBUG && MYTEST)
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else
        Console.WriteLine("DEBUG and MYTEST are not defined");
#endif
    }
}
```

<span data-ttu-id="849dd-132">В следующем примере показано, как тестировать разные целевые платформы для использования более новых интерфейсов API, когда это возможно:</span><span class="sxs-lookup"><span data-stu-id="849dd-132">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a><span data-ttu-id="849dd-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="849dd-133">See also</span></span>

- [<span data-ttu-id="849dd-134">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="849dd-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="849dd-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="849dd-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="849dd-136">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="849dd-136">C# Preprocessor Directives</span></span>](index.md)
- [<span data-ttu-id="849dd-137">Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug</span><span class="sxs-lookup"><span data-stu-id="849dd-137">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
