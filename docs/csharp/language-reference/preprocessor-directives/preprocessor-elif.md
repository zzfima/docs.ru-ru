---
title: '#elif. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: b04db4bd23a459043efec59b8ebf9d322defbcf7
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608582"
---
# <a name="elif-c-reference"></a><span data-ttu-id="bbe91-102">#elif (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="bbe91-102">#elif (C# Reference)</span></span>
<span data-ttu-id="bbe91-103">Директива `#elif` позволяет создать составную условную директиву.</span><span class="sxs-lookup"><span data-stu-id="bbe91-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="bbe91-104">Выражение `#elif` будет вычисляться в том случае, если ни одна из предшествующих директив [#if](./preprocessor-if.md) или необязательных директив `#elif` после вычисления выражения не возвращает значение `true`.</span><span class="sxs-lookup"><span data-stu-id="bbe91-104">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="bbe91-105">Если после вычисления выражения `#elif` возвращается значение `true`, компилятор вычисляет весь код между директивой `#elif` и следующей условной директивой.</span><span class="sxs-lookup"><span data-stu-id="bbe91-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="bbe91-106">Например:</span><span class="sxs-lookup"><span data-stu-id="bbe91-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="bbe91-107">Для вычисления нескольких символов можно использовать операторы `==` (равенство), `!=` (неравенство), `&&` (И) и `||` (ИЛИ).</span><span class="sxs-lookup"><span data-stu-id="bbe91-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="bbe91-108">Можно также группировать символы и операторы при помощи скобок.</span><span class="sxs-lookup"><span data-stu-id="bbe91-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbe91-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="bbe91-109">Remarks</span></span>  
 <span data-ttu-id="bbe91-110">Применение `#elif` эквивалентно следующему:</span><span class="sxs-lookup"><span data-stu-id="bbe91-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="bbe91-111">Директива `#elif` позволяет упростить код, поскольку для каждой директивы `#if` требуется отдельная директива [#endif](./preprocessor-endif.md), тогда как `#elif` можно использовать без соответствующей директивы `#endif`.</span><span class="sxs-lookup"><span data-stu-id="bbe91-111">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="bbe91-112">В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#elif`.</span><span class="sxs-lookup"><span data-stu-id="bbe91-112">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe91-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bbe91-113">See also</span></span>

- [<span data-ttu-id="bbe91-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bbe91-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bbe91-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bbe91-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bbe91-116">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="bbe91-116">C# Preprocessor Directives</span></span>](./index.md)
