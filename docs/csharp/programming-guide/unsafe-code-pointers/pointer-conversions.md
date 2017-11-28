---
title: "Преобразования указателей (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 36589d139c91e04d9e3d8b31281a91c26b85a5d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="402c0-102">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="402c0-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="402c0-103">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="402c0-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="402c0-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="402c0-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="402c0-105">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="402c0-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="402c0-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="402c0-106">From</span></span>|<span data-ttu-id="402c0-107">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="402c0-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="402c0-108">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="402c0-108">Any pointer type</span></span>|<span data-ttu-id="402c0-109">void*</span><span class="sxs-lookup"><span data-stu-id="402c0-109">void*</span></span>|  
|<span data-ttu-id="402c0-110">null</span><span class="sxs-lookup"><span data-stu-id="402c0-110">null</span></span>|<span data-ttu-id="402c0-111">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="402c0-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="402c0-112">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="402c0-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="402c0-113">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="402c0-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="402c0-114">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="402c0-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="402c0-115">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="402c0-115">From</span></span>|<span data-ttu-id="402c0-116">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="402c0-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="402c0-117">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="402c0-117">Any pointer type</span></span>|<span data-ttu-id="402c0-118">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="402c0-118">Any other pointer type</span></span>|  
|<span data-ttu-id="402c0-119">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="402c0-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="402c0-120">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="402c0-120">Any pointer type</span></span>|  
|<span data-ttu-id="402c0-121">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="402c0-121">Any pointer type</span></span>|<span data-ttu-id="402c0-122">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="402c0-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="402c0-123">Пример</span><span class="sxs-lookup"><span data-stu-id="402c0-123">Example</span></span>  
 <span data-ttu-id="402c0-124">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="402c0-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="402c0-125">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="402c0-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="402c0-126">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="402c0-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="402c0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="402c0-127">See Also</span></span>  
 [<span data-ttu-id="402c0-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="402c0-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="402c0-129">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="402c0-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="402c0-130">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="402c0-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="402c0-131">Типы</span><span class="sxs-lookup"><span data-stu-id="402c0-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="402c0-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="402c0-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="402c0-133">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="402c0-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="402c0-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="402c0-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
