---
title: Массивы как объекты (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: f1abe10839c30d48f56ac6044d75d290a59b4cce
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505563"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="f353d-102">Массивы как объекты (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f353d-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="f353d-103">В C# массивы представляют собой реальные объекты, а не просто адресуемые области непрерывной памяти, как в C и C++.</span><span class="sxs-lookup"><span data-stu-id="f353d-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="f353d-104"><xref:System.Array> — это абстрактный базовый тип для всех типов массивов.</span><span class="sxs-lookup"><span data-stu-id="f353d-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="f353d-105">Вы можете использовать свойства и другие члены класса, входящие в <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="f353d-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="f353d-106">Например, с помощью свойства <xref:System.Array.Length%2A> можно получить длину массива.</span><span class="sxs-lookup"><span data-stu-id="f353d-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="f353d-107">В следующем коде значение длины массива `numbers` (`5`) присваивается переменной с именем `lengthOfNumbers`:</span><span class="sxs-lookup"><span data-stu-id="f353d-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 <span data-ttu-id="f353d-108">В классе <xref:System.Array> представлено множество других полезных методов и свойств для сортировки, поиска и копирования массивов.</span><span class="sxs-lookup"><span data-stu-id="f353d-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f353d-109">Пример</span><span class="sxs-lookup"><span data-stu-id="f353d-109">Example</span></span>

 <span data-ttu-id="f353d-110">В этом примере используется свойство <xref:System.Array.Rank%2A>, позволяющее отобразить число измерений массива.</span><span class="sxs-lookup"><span data-stu-id="f353d-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f353d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f353d-111">See Also</span></span>

- [<span data-ttu-id="f353d-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f353d-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f353d-113">Массивы</span><span class="sxs-lookup"><span data-stu-id="f353d-113">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="f353d-114">Одномерные массивы</span><span class="sxs-lookup"><span data-stu-id="f353d-114">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [<span data-ttu-id="f353d-115">Многомерные массивы</span><span class="sxs-lookup"><span data-stu-id="f353d-115">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [<span data-ttu-id="f353d-116">Массивы массивов</span><span class="sxs-lookup"><span data-stu-id="f353d-116">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
