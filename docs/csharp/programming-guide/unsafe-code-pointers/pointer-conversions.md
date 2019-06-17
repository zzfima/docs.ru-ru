---
title: Руководство по программированию на C#. Преобразования указателей
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 3cef2f2d2af2d285504daea14aa57c55b9e9a21b
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833462"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="8fbe8-102">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="8fbe8-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="8fbe8-103">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="8fbe8-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="8fbe8-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="8fbe8-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="8fbe8-105">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="8fbe8-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="8fbe8-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="8fbe8-106">From</span></span>|<span data-ttu-id="8fbe8-107">Кому</span><span class="sxs-lookup"><span data-stu-id="8fbe8-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="8fbe8-108">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="8fbe8-108">Any pointer type</span></span>|<span data-ttu-id="8fbe8-109">void\*</span><span class="sxs-lookup"><span data-stu-id="8fbe8-109">void\*</span></span>|  
|<span data-ttu-id="8fbe8-110">null</span><span class="sxs-lookup"><span data-stu-id="8fbe8-110">null</span></span>|<span data-ttu-id="8fbe8-111">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="8fbe8-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="8fbe8-112">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="8fbe8-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="8fbe8-113">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8fbe8-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="8fbe8-114">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="8fbe8-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="8fbe8-115">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="8fbe8-115">From</span></span>|<span data-ttu-id="8fbe8-116">Кому</span><span class="sxs-lookup"><span data-stu-id="8fbe8-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="8fbe8-117">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="8fbe8-117">Any pointer type</span></span>|<span data-ttu-id="8fbe8-118">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="8fbe8-118">Any other pointer type</span></span>|  
|<span data-ttu-id="8fbe8-119">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="8fbe8-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="8fbe8-120">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="8fbe8-120">Any pointer type</span></span>|  
|<span data-ttu-id="8fbe8-121">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="8fbe8-121">Any pointer type</span></span>|<span data-ttu-id="8fbe8-122">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="8fbe8-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8fbe8-123">Пример</span><span class="sxs-lookup"><span data-stu-id="8fbe8-123">Example</span></span>  
 <span data-ttu-id="8fbe8-124">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="8fbe8-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="8fbe8-125">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="8fbe8-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="8fbe8-126">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="8fbe8-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8fbe8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8fbe8-127">See also</span></span>

- [<span data-ttu-id="8fbe8-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8fbe8-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8fbe8-129">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="8fbe8-129">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="8fbe8-130">Типы</span><span class="sxs-lookup"><span data-stu-id="8fbe8-130">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="8fbe8-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="8fbe8-131">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="8fbe8-132">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="8fbe8-132">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="8fbe8-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="8fbe8-133">stackalloc</span></span>](../../../csharp/language-reference/operators/stackalloc.md)
