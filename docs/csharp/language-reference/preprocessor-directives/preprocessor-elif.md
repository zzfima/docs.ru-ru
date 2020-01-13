---
title: '#elif. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: c78818f40b76414d289af6c704ff019b63befe37
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712576"
---
# <a name="elif-c-reference"></a><span data-ttu-id="21b6d-102">#elif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="21b6d-102">#elif (C# Reference)</span></span>
<span data-ttu-id="21b6d-103">Директива `#elif` позволяет создать составную условную директиву.</span><span class="sxs-lookup"><span data-stu-id="21b6d-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="21b6d-104">Выражение `#elif` будет вычисляться в том случае, если ни одна из предшествующих директив [#if](./preprocessor-if.md) или необязательных директив `#elif` после вычисления выражения не возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="21b6d-104">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="21b6d-105">Если после вычисления выражения `#elif` возвращается значение `true`, компилятор вычисляет весь код между директивой `#elif` и следующей условной директивой.</span><span class="sxs-lookup"><span data-stu-id="21b6d-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="21b6d-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="21b6d-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="21b6d-107">Для вычисления нескольких символов можно использовать операторы `==` (равенство), `!=` (неравенство), `&&` (И) и `||` (ИЛИ).</span><span class="sxs-lookup"><span data-stu-id="21b6d-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="21b6d-108">Можно также группировать символы и операторы при помощи скобок.</span><span class="sxs-lookup"><span data-stu-id="21b6d-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21b6d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="21b6d-109">Remarks</span></span>  
 <span data-ttu-id="21b6d-110">Применение `#elif` эквивалентно следующему:</span><span class="sxs-lookup"><span data-stu-id="21b6d-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="21b6d-111">Директива `#elif` позволяет упростить код, поскольку для каждой директивы `#if` требуется отдельная директива [#endif](./preprocessor-endif.md), тогда как `#elif` можно использовать без соответствующей директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="21b6d-111">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="21b6d-112">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#elif`.</span><span class="sxs-lookup"><span data-stu-id="21b6d-112">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b6d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="21b6d-113">See also</span></span>

- [<span data-ttu-id="21b6d-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="21b6d-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="21b6d-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="21b6d-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="21b6d-116">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="21b6d-116">C# Preprocessor Directives</span></span>](./index.md)
