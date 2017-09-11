---
title: "#<a name=\"define-c-reference\"></a>#define (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
dev_langs:
- CSharp
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8ace15f79480c9aeb0fcb4c7d46c207d4904cef0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="define-c-reference"></a><span data-ttu-id="c76d7-102">#define (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c76d7-102">#define (C# Reference)</span></span>
<span data-ttu-id="c76d7-103">`#define` позволяет определить символ.</span><span class="sxs-lookup"><span data-stu-id="c76d7-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="c76d7-104">При использовании символа в качестве выражения, которое передается директиве [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), выражение будет иметь значение `true`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="c76d7-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
  
 <span data-ttu-id="c76d7-105">`#`  `define`   `DEBUG`</span><span class="sxs-lookup"><span data-stu-id="c76d7-105">`#`  `define`   `DEBUG`</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c76d7-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c76d7-106">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c76d7-107">Директиву `#define` нельзя использовать для объявления значений констант, как это обычно делается в C и C++.</span><span class="sxs-lookup"><span data-stu-id="c76d7-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="c76d7-108">Для определения констант в C# следует использовать статические элементы класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="c76d7-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="c76d7-109">При наличии нескольких констант имеет смысл создать для них отдельный класс "Constants".</span><span class="sxs-lookup"><span data-stu-id="c76d7-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="c76d7-110">Символы можно использовать для указания условий компиляции.</span><span class="sxs-lookup"><span data-stu-id="c76d7-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="c76d7-111">Для проверки символов можно использовать директивы [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) или [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="c76d7-111">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="c76d7-112">Для условной компиляции также можно использовать атрибут `conditional`.</span><span class="sxs-lookup"><span data-stu-id="c76d7-112">You can also use the `conditional` attribute to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="c76d7-113">Можно определить символ, но нельзя назначить символу значение.</span><span class="sxs-lookup"><span data-stu-id="c76d7-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="c76d7-114">Директива `#define` должна находиться в файле перед использованием любых инструкций, которые также не являются директивами препроцессора.</span><span class="sxs-lookup"><span data-stu-id="c76d7-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="c76d7-115">Можно также определить символ с помощью параметра компилятора [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c76d7-115">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="c76d7-116">Для отмены определения символа служит директива [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="c76d7-116">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="c76d7-117">Символ, определенный с помощью `/define` или `#define`, не конфликтует с одноименной переменной.</span><span class="sxs-lookup"><span data-stu-id="c76d7-117">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="c76d7-118">Имя переменной не должно передаваться директиве препроцессора, а символ может вычисляться только директивой препроцессора.</span><span class="sxs-lookup"><span data-stu-id="c76d7-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="c76d7-119">Область символа, которая была создана с помощью директивы `#define`, — это файл, в котором был определен символ.</span><span class="sxs-lookup"><span data-stu-id="c76d7-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="c76d7-120">Как показано в следующем примере, необходимо поместить директивы `#define` в верхнюю часть файла.</span><span class="sxs-lookup"><span data-stu-id="c76d7-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="c76d7-121">Пример отмены определения символа см. в разделе [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="c76d7-121">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76d7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c76d7-122">See Also</span></span>  
 <span data-ttu-id="c76d7-123">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c76d7-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c76d7-124">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c76d7-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c76d7-125">[Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="c76d7-125">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="c76d7-126">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="c76d7-126">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 <span data-ttu-id="c76d7-127">[Практическое руководство. Условная компиляция с использованием атрибутов Trace и Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span><span class="sxs-lookup"><span data-stu-id="c76d7-127">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span></span>  
 <span data-ttu-id="c76d7-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span><span class="sxs-lookup"><span data-stu-id="c76d7-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span></span>  
 [<span data-ttu-id="c76d7-129">#if</span><span class="sxs-lookup"><span data-stu-id="c76d7-129">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)

