---
title: Справочник по C#. Метод partial
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 62efd8b47fb565316b417a65e1b0fe37e40786c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713226"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="0502f-102">Метод partial (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0502f-102">partial method (C# Reference)</span></span>

<span data-ttu-id="0502f-103">Сигнатура разделяемого метода определяется в одной части разделяемого типа, а его реализация — в другой части этого типа.</span><span class="sxs-lookup"><span data-stu-id="0502f-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="0502f-104">С помощью разделяемых методов разработчики классов могут при необходимости реализовывать ловушки методов, которые схожи с обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="0502f-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="0502f-105">Если реализация не предоставлена, компилятор удаляет сигнатуру во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="0502f-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="0502f-106">В отношении разделяемых методов применяются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="0502f-106">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="0502f-107">Сигнатуры в обеих частях разделяемого типа должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="0502f-107">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="0502f-108">Метод должен возвращать значение void.</span><span class="sxs-lookup"><span data-stu-id="0502f-108">The method must return void.</span></span>

- <span data-ttu-id="0502f-109">Модификаторы доступа не допускаются.</span><span class="sxs-lookup"><span data-stu-id="0502f-109">No access modifiers are allowed.</span></span> <span data-ttu-id="0502f-110">Разделяемые методы являются неявно частными.</span><span class="sxs-lookup"><span data-stu-id="0502f-110">Partial methods are implicitly private.</span></span>

<span data-ttu-id="0502f-111">В следующем примере показан разделяемый метод, определенный в двух частях разделяемого класса:</span><span class="sxs-lookup"><span data-stu-id="0502f-111">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="0502f-112">Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0502f-112">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0502f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0502f-113">See also</span></span>

- [<span data-ttu-id="0502f-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0502f-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0502f-115">Тип partial</span><span class="sxs-lookup"><span data-stu-id="0502f-115">partial type</span></span>](partial-type.md)
