---
title: Псевдоним extern. Справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 8a33b466bbe75b84d6cd28ebd6f4fc57695aa420
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452441"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="2dfab-102">Псевдоним extern (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="2dfab-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="2dfab-103">Иногда может потребоваться сослаться на две версии сборок, которые имеют одинаковые полные имена типов.</span><span class="sxs-lookup"><span data-stu-id="2dfab-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="2dfab-104">Например, если необходимо использовать две или более версии сборки в одном приложении.</span><span class="sxs-lookup"><span data-stu-id="2dfab-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="2dfab-105">Используя внешний псевдоним сборки, пространства имен для каждой сборки можно перенести внутрь пространств имен корневого уровня с именованием по псевдониму, что позволяет использовать их в одном файле.</span><span class="sxs-lookup"><span data-stu-id="2dfab-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2dfab-106">Ключевое слово [extern](../../../csharp/language-reference/keywords/extern.md) также используется в качестве модификатора метода, объявляющего метод, написанный в неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="2dfab-106">The [extern](../../../csharp/language-reference/keywords/extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="2dfab-107">Для ссылки на две сборки с одинаковыми полными именами типов псевдоним необходимо указать в командной строке следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2dfab-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="2dfab-108">При этом создаются внешние псевдонимы `GridV1` и `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="2dfab-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="2dfab-109">Чтобы использовать эти псевдонимы в программе, сошлитесь на них с помощью ключевого слова `extern`.</span><span class="sxs-lookup"><span data-stu-id="2dfab-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="2dfab-110">Например:</span><span class="sxs-lookup"><span data-stu-id="2dfab-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="2dfab-111">Каждое объявление псевдонима extern создает дополнительное пространство имен корневого уровня, которое является параллельным для глобального пространства имен (но не находится в его пределах).</span><span class="sxs-lookup"><span data-stu-id="2dfab-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="2dfab-112">Таким образом, на типы из каждой сборки можно ссылаться без неоднозначности, используя их полное имя, размещенное в соответствующем пространстве имен-псевдониме.</span><span class="sxs-lookup"><span data-stu-id="2dfab-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="2dfab-113">В предыдущем примере `GridV1::Grid` является элементом управления сетки из `grid.dll`, а `GridV2::Grid` — элементом управления сетки из `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="2dfab-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2dfab-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="2dfab-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2dfab-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2dfab-115">See also</span></span>

- [<span data-ttu-id="2dfab-116">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="2dfab-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="2dfab-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2dfab-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2dfab-118">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="2dfab-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="2dfab-119">Ключевые слова, используемые для пространств имен</span><span class="sxs-lookup"><span data-stu-id="2dfab-119">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)
- [<span data-ttu-id="2dfab-120">:: Оператор</span><span class="sxs-lookup"><span data-stu-id="2dfab-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)
- [<span data-ttu-id="2dfab-121">/reference (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="2dfab-121">/reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
