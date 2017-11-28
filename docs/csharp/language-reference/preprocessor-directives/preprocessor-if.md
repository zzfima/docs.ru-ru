---
title: "#<a name=\"if-c-reference\"></a>#if (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#if'
helpviewer_keywords: '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4e3b79f64f5190d48d7248726ecdf031ad685e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="if-c-reference"></a><span data-ttu-id="8d4af-102">#if (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8d4af-102">#if (C# Reference)</span></span>
<span data-ttu-id="8d4af-103">Когда компилятор C# встречает директиву `#if`, за которой следует директива [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), код между этими директивами он компилирует только в том случае, когда определен указанный символ.</span><span class="sxs-lookup"><span data-stu-id="8d4af-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) directive, it will compile the code between the directives only if the specified symbol is defined.</span></span>  <span data-ttu-id="8d4af-104">В отличие от C и C++, здесь нельзя назначить символу числовое значение. Оператор #if языка C# является логическим и проверяет только одно условие — определен ли указанный символ.</span><span class="sxs-lookup"><span data-stu-id="8d4af-104">Unlike C and C++, you cannot assign a numeric value to a symbol; the #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="8d4af-105">Например:</span><span class="sxs-lookup"><span data-stu-id="8d4af-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 <span data-ttu-id="8d4af-106">Операторы [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (равенство) и [! =](../../../csharp/language-reference/operators/not-equal-operator.md) (неравенство) вы можете использовать только для проверки значений [true](../../../csharp/language-reference/keywords/true.md) или [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="8d4af-106">You can use the operators [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (equality), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (inequality) only to test for [true](../../../csharp/language-reference/keywords/true.md) or [false](../../../csharp/language-reference/keywords/false.md) .</span></span> <span data-ttu-id="8d4af-107">Значение true означает, что символ определен.</span><span class="sxs-lookup"><span data-stu-id="8d4af-107">True means the symbol is defined.</span></span> <span data-ttu-id="8d4af-108">Инструкция `#if DEBUG` имеет то же значение, что и `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="8d4af-108">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="8d4af-109">Вы можете использовать операторы [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (логическое И), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (логическое ИЛИ) и [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="8d4af-109">You can use the operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (and), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (or), and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="8d4af-110">(логическое НЕ) для проверки нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="8d4af-110">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="8d4af-111">Можно также группировать символы и операторы при помощи скобок.</span><span class="sxs-lookup"><span data-stu-id="8d4af-111">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d4af-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d4af-112">Remarks</span></span>  
 <span data-ttu-id="8d4af-113">`#if`, как и директивы [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) и [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md), позволяет включить или исключить код в зависимости от существования одного или нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="8d4af-113">`#if`, along with the [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), and [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="8d4af-114">Это может быть полезно при компиляции кода для отладки или для определенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8d4af-114">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>  
  
 <span data-ttu-id="8d4af-115">Условные директивы, начинающиеся с директивы `#if`, должны явным образом завершаться директивой `#endif`.</span><span class="sxs-lookup"><span data-stu-id="8d4af-115">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>  
  
 <span data-ttu-id="8d4af-116">`#define` позволяет определить символ, чтобы директива `#if`, которой передается этот символ, возвращала значение `true`.</span><span class="sxs-lookup"><span data-stu-id="8d4af-116">`#define` lets you define a symbol, such that, by using the symbol as the expression passed to the `#if` directive, the expression will evaluate to `true`.</span></span>  
  
 <span data-ttu-id="8d4af-117">Также символ можно определить с помощью параметра компилятора [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="8d4af-117">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="8d4af-118">Для отмены определения символа служит директива [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="8d4af-118">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="8d4af-119">Символ, определенный с помощью `/define` или `#define`, не конфликтует с одноименной переменной.</span><span class="sxs-lookup"><span data-stu-id="8d4af-119">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="8d4af-120">Соответственно, имя переменной не должно передаваться директиве препроцессора, а символ может использоваться только в директиве препроцессора.</span><span class="sxs-lookup"><span data-stu-id="8d4af-120">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="8d4af-121">Символ, создаваемый с помощью `#define`, будет определен в пределах того файл, в котором он определен.</span><span class="sxs-lookup"><span data-stu-id="8d4af-121">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d4af-122">Пример</span><span class="sxs-lookup"><span data-stu-id="8d4af-122">Example</span></span>  
  
```csharp
// preprocessor_if.cs  
#define DEBUG
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
  
 <span data-ttu-id="8d4af-123">**Определение символов DEBUG и MYTEST**</span><span class="sxs-lookup"><span data-stu-id="8d4af-123">**DEBUG and MYTEST are defined**</span></span>  
## <a name="see-also"></a><span data-ttu-id="8d4af-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8d4af-124">See Also</span></span>  
 [<span data-ttu-id="8d4af-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8d4af-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8d4af-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8d4af-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8d4af-127">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="8d4af-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
