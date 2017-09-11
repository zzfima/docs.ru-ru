---
title: "#<a name=\"elif-c-reference\"></a>elif (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#elif'
dev_langs:
- CSharp
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
caps.latest.revision: 14
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
ms.openlocfilehash: 7635365222621101253ecb2a3676701c2e6a2b88
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="elif-c-reference"></a><span data-ttu-id="ba80c-102">#elif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="ba80c-102">#elif (C# Reference)</span></span>
<span data-ttu-id="ba80c-103">Директива `#elif` позволяет создать составную условную директиву.</span><span class="sxs-lookup"><span data-stu-id="ba80c-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="ba80c-104">Выражение `#elif` будет вычисляться в том случае, если ни одна из предшествующих директив [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) или необязательных директив `#elif` после вычисления выражения не возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ba80c-104">The `#elif` expression will be evaluated if neither the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="ba80c-105">Если после вычисления выражения `#elif` возвращается значение `true`, компилятор вычисляет весь код между директивой `#elif` и следующей условной директивой.</span><span class="sxs-lookup"><span data-stu-id="ba80c-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="ba80c-106">Например:</span><span class="sxs-lookup"><span data-stu-id="ba80c-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="ba80c-107">Для вычисления нескольких символов можно использовать операторы `==` (равенство), `!=` (неравенство), `&&` (И) и `||` (ИЛИ).</span><span class="sxs-lookup"><span data-stu-id="ba80c-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="ba80c-108">Можно также группировать символы и операторы при помощи скобок.</span><span class="sxs-lookup"><span data-stu-id="ba80c-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba80c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba80c-109">Remarks</span></span>  
 <span data-ttu-id="ba80c-110">Применение `#elif` эквивалентно следующему:</span><span class="sxs-lookup"><span data-stu-id="ba80c-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="ba80c-111">Директива `#elif` позволяет упростить код, поскольку для каждой директивы `#if` требуется отдельная директива [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), тогда как `#elif` можно использовать без соответствующей директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="ba80c-111">Using `#elif` is simpler, because each `#if` requires a [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="ba80c-112">В разделе [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) приводится пример использования директивы `#elif`.</span><span class="sxs-lookup"><span data-stu-id="ba80c-112">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba80c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ba80c-113">See Also</span></span>  
 <span data-ttu-id="ba80c-114">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba80c-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ba80c-115">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ba80c-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ba80c-116">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="ba80c-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

