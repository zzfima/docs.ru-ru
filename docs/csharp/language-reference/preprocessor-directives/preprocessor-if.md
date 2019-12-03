---
title: '#Справочник по C#. Директива препроцессора if'
ms.custom: seodec18
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: e467a890e971e6c6f2c681ee503d7c7ead19a1e4
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552447"
---
# <a name="if-c-reference"></a><span data-ttu-id="90b3b-102">#if (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="90b3b-102">#if (C# Reference)</span></span>

<span data-ttu-id="90b3b-103">Когда компилятор C# встречает директиву `#if`, за которой следует директива [#endif](preprocessor-endif.md), код между этими директивами он компилирует, только когда определен указанный символ.</span><span class="sxs-lookup"><span data-stu-id="90b3b-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="90b3b-104">В отличие от С и С++ здесь нельзя назначить символу числовое значение.</span><span class="sxs-lookup"><span data-stu-id="90b3b-104">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="90b3b-105">Оператор #if в C# является логическим. Он проверяет только одно условие — определен ли указанный символ.</span><span class="sxs-lookup"><span data-stu-id="90b3b-105">The #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="90b3b-106">Например:</span><span class="sxs-lookup"><span data-stu-id="90b3b-106">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="90b3b-107">Операторы [==](../operators/equality-operators.md#equality-operator-) (равенство) и [!=](../operators/equality-operators.md#inequality-operator-) (неравенство) можно использовать только для проверки значений [bool](../builtin-types/bool.md) `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="90b3b-107">You can use the operators [==](../operators/equality-operators.md#equality-operator-) (equality) and [!=](../operators/equality-operators.md#inequality-operator-) (inequality) only to test for the [bool](../builtin-types/bool.md) values `true` or `false`.</span></span> <span data-ttu-id="90b3b-108">Значение true означает, что символ определен.</span><span class="sxs-lookup"><span data-stu-id="90b3b-108">True means the symbol is defined.</span></span> <span data-ttu-id="90b3b-109">Инструкция `#if DEBUG` имеет то же значение, что и `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="90b3b-109">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="90b3b-110">Вы можете использовать операторы [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) (логическое И), [& #124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) (логическое ИЛИ) и [!](../operators/boolean-logical-operators.md#logical-negation-operator-)</span><span class="sxs-lookup"><span data-stu-id="90b3b-110">You can use the operators [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) (and), [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) (or), and [!](../operators/boolean-logical-operators.md#logical-negation-operator-)</span></span> <span data-ttu-id="90b3b-111">(логическое НЕ) для проверки нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="90b3b-111">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="90b3b-112">Можно также группировать символы и операторы при помощи скобок.</span><span class="sxs-lookup"><span data-stu-id="90b3b-112">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="90b3b-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="90b3b-113">Remarks</span></span>

<span data-ttu-id="90b3b-114">`#if`, как и директивы [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) и [#undef](preprocessor-undef.md), позволяет включить или исключить код в зависимости от существования одного или нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="90b3b-114">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="90b3b-115">Это может быть полезно при компиляции кода для отладки или для определенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="90b3b-115">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="90b3b-116">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="90b3b-116">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="90b3b-117">`#define` позволяет определить символ,</span><span class="sxs-lookup"><span data-stu-id="90b3b-117">`#define` lets you define a symbol.</span></span> <span data-ttu-id="90b3b-118">чтобы директива `#if`, которой передается этот символ, возвращала значение `true`.</span><span class="sxs-lookup"><span data-stu-id="90b3b-118">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="90b3b-119">Также символ можно определить с помощью параметра компилятора [-define](../compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="90b3b-119">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="90b3b-120">Для отмены определения символа служит директива [#undef](preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="90b3b-120">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="90b3b-121">Символ, определенный с помощью `-define` или `#define`, не конфликтует с одноименной переменной.</span><span class="sxs-lookup"><span data-stu-id="90b3b-121">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="90b3b-122">Соответственно, имя переменной не должно передаваться директиве препроцессора, а символ может использоваться только в директиве препроцессора.</span><span class="sxs-lookup"><span data-stu-id="90b3b-122">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="90b3b-123">Символ, создаваемый с помощью `#define`, будет определен в пределах того файл, в котором он определен.</span><span class="sxs-lookup"><span data-stu-id="90b3b-123">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="90b3b-124">Система сборки также учитывает символы препроцессора, представляющие [целевые платформы](../../../standard/frameworks.md) в проектах в стиле SDK.</span><span class="sxs-lookup"><span data-stu-id="90b3b-124">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md) in SDK-style projects.</span></span> <span data-ttu-id="90b3b-125">Они полезны при создании приложений, предназначенных для нескольких реализаций или версий .NET.</span><span class="sxs-lookup"><span data-stu-id="90b3b-125">They're useful when creating applications that can target more than one .NET implementation or version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> <span data-ttu-id="90b3b-126">Для традиционных проектов .NET Framework необходимо вручную настроить символы условной компиляции для различных целевых платформ в Visual Studio с помощью страниц свойств проекта.</span><span class="sxs-lookup"><span data-stu-id="90b3b-126">For traditional .NET Framework projects, you have to manually configure the conditional compilation symbols for the different target frameworks in Visual Studio via the project's properties pages.</span></span>

<span data-ttu-id="90b3b-127">Другие предопределенные символы включают константы DEBUG и TRACE.</span><span class="sxs-lookup"><span data-stu-id="90b3b-127">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="90b3b-128">Вы можете переопределить значения для проектов с помощью `#define`.</span><span class="sxs-lookup"><span data-stu-id="90b3b-128">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="90b3b-129">Например, символ DEBUG автоматически устанавливается в зависимости от свойств конфигурации сборки (в режиме отладки или выпуска).</span><span class="sxs-lookup"><span data-stu-id="90b3b-129">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="90b3b-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="90b3b-130">Examples</span></span>

<span data-ttu-id="90b3b-131">В следующем примере показано, как определить символ MYTEST в файле и затем протестировать значения символов MYTEST и DEBUG.</span><span class="sxs-lookup"><span data-stu-id="90b3b-131">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="90b3b-132">Выходные данные этого примера зависят от режима конфигурации, в котором создан проект (режим отладки или выпуска).</span><span class="sxs-lookup"><span data-stu-id="90b3b-132">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

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

<span data-ttu-id="90b3b-133">В следующем примере показано, как тестировать разные целевые платформы для использования более новых интерфейсов API, когда это возможно:</span><span class="sxs-lookup"><span data-stu-id="90b3b-133">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="90b3b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="90b3b-134">See also</span></span>

- [<span data-ttu-id="90b3b-135">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="90b3b-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="90b3b-136">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="90b3b-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="90b3b-137">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="90b3b-137">C# Preprocessor Directives</span></span>](index.md)
- <span data-ttu-id="90b3b-138">[Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).</span><span class="sxs-lookup"><span data-stu-id="90b3b-138">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)</span></span>
