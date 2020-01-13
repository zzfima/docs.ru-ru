---
title: Руководство по программированию на C#. Неявно типизированные массивы
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 943760af30422cd333fdff65cdf678108c9d9564
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705721"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="e61a6-102">Неявно типизированные массивы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e61a6-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="e61a6-103">Вы можете создать неявно типизированный массив, тип экземпляра которого будет определяться на основе элементов, указанных в инициализаторе массива.</span><span class="sxs-lookup"><span data-stu-id="e61a6-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="e61a6-104">В отношении таких массивов действуют правила для неявно типизированных переменных.</span><span class="sxs-lookup"><span data-stu-id="e61a6-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="e61a6-105">Дополнительные сведения см. в статье [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md) (Неявно типизированные локальные переменные).</span><span class="sxs-lookup"><span data-stu-id="e61a6-105">For more information, see [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

<span data-ttu-id="e61a6-106">Неявно типизированные массивы обычно используются в выражениях запросов вместе с анонимными типами, а также инициализаторами объектов и коллекций.</span><span class="sxs-lookup"><span data-stu-id="e61a6-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>

<span data-ttu-id="e61a6-107">В следующих примерах демонстрируется создание неявно типизированного массива:</span><span class="sxs-lookup"><span data-stu-id="e61a6-107">The following examples show how to create an implicitly-typed array:</span></span>

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

<span data-ttu-id="e61a6-108">Обратите внимание, что в предыдущем примере с неявно типизированными массивами в левой части выражения инициализации не используются квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="e61a6-108">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="e61a6-109">Также обратите внимание, что массивы массивов инициализируются с помощью выражения `new []`, как и одномерные массивы.</span><span class="sxs-lookup"><span data-stu-id="e61a6-109">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>

## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="e61a6-110">Неявно типизированные массивы в инициализаторах объектов</span><span class="sxs-lookup"><span data-stu-id="e61a6-110">Implicitly-typed Arrays in Object Initializers</span></span>

<span data-ttu-id="e61a6-111">При создании анонимного типа, содержащего массив, этот массив необходимо неявно типизировать в инициализаторе объекта типа.</span><span class="sxs-lookup"><span data-stu-id="e61a6-111">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="e61a6-112">В следующем примере `contacts` представляет собой неявно типизированный массив анонимных типов, каждый из которых содержит массив с именем `PhoneNumbers`.</span><span class="sxs-lookup"><span data-stu-id="e61a6-112">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="e61a6-113">Обратите внимание, что внутри инициализаторов объектов не используется ключевое слово `var`.</span><span class="sxs-lookup"><span data-stu-id="e61a6-113">Note that the `var` keyword is not used inside the object initializers.</span></span>

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a><span data-ttu-id="e61a6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e61a6-114">See also</span></span>

- [<span data-ttu-id="e61a6-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e61a6-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e61a6-116">Неявно типизированные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="e61a6-116">Implicitly Typed Local Variables</span></span>](../classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="e61a6-117">Массивы</span><span class="sxs-lookup"><span data-stu-id="e61a6-117">Arrays</span></span>](./index.md)
- [<span data-ttu-id="e61a6-118">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="e61a6-118">Anonymous Types</span></span>](../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="e61a6-119">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="e61a6-119">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="e61a6-120">var</span><span class="sxs-lookup"><span data-stu-id="e61a6-120">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="e61a6-121">LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="e61a6-121">LINQ in C#</span></span>](../../linq/index.md)
