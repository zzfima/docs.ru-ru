---
title: Руководство по программированию на C#. Массивы как объекты
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 8500cf508b77a0fa7e348ce0fe6b1f16fd2bab25
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977186"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="c20f2-102">Массивы как объекты (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="c20f2-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="c20f2-103">В C# массивы представляют собой реальные объекты, а не просто адресуемые области непрерывной памяти, как в C и C++.</span><span class="sxs-lookup"><span data-stu-id="c20f2-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="c20f2-104"><xref:System.Array> — это абстрактный базовый тип для всех типов массивов.</span><span class="sxs-lookup"><span data-stu-id="c20f2-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="c20f2-105">Вы можете использовать свойства и другие члены класса, входящие в <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="c20f2-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="c20f2-106">Например, с помощью свойства <xref:System.Array.Length%2A> можно получить длину массива.</span><span class="sxs-lookup"><span data-stu-id="c20f2-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="c20f2-107">В следующем коде значение длины массива `numbers` (`5`) присваивается переменной с именем `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="c20f2-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]  
  
 <span data-ttu-id="c20f2-108">В классе <xref:System.Array> представлено множество других полезных методов и свойств для сортировки, поиска и копирования массивов.</span><span class="sxs-lookup"><span data-stu-id="c20f2-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c20f2-109">Пример</span><span class="sxs-lookup"><span data-stu-id="c20f2-109">Example</span></span>

 <span data-ttu-id="c20f2-110">В этом примере используется свойство <xref:System.Array.Rank%2A>, позволяющее отобразить число измерений массива.</span><span class="sxs-lookup"><span data-stu-id="c20f2-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c20f2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c20f2-111">See also</span></span>

- [<span data-ttu-id="c20f2-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c20f2-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c20f2-113">Массивы</span><span class="sxs-lookup"><span data-stu-id="c20f2-113">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="c20f2-114">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="c20f2-114">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [<span data-ttu-id="c20f2-115">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="c20f2-115">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)
- [<span data-ttu-id="c20f2-116">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="c20f2-116">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
