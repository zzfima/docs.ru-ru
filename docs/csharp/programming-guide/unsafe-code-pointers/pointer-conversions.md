---
title: Руководство по программированию на C#. Преобразования указателей
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: b0a517eacc505376c9502e9d095c7aac0cd54555
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417535"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="f53e6-102">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f53e6-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="f53e6-103">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="f53e6-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="f53e6-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="f53e6-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="f53e6-105">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="f53e6-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="f53e6-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="f53e6-106">From</span></span>|<span data-ttu-id="f53e6-107">Кому</span><span class="sxs-lookup"><span data-stu-id="f53e6-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="f53e6-108">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="f53e6-108">Any pointer type</span></span>|<span data-ttu-id="f53e6-109">void\*</span><span class="sxs-lookup"><span data-stu-id="f53e6-109">void\*</span></span>|  
|<span data-ttu-id="f53e6-110">null</span><span class="sxs-lookup"><span data-stu-id="f53e6-110">null</span></span>|<span data-ttu-id="f53e6-111">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="f53e6-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="f53e6-112">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="f53e6-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="f53e6-113">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f53e6-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="f53e6-114">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="f53e6-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="f53e6-115">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="f53e6-115">From</span></span>|<span data-ttu-id="f53e6-116">Кому</span><span class="sxs-lookup"><span data-stu-id="f53e6-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="f53e6-117">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="f53e6-117">Any pointer type</span></span>|<span data-ttu-id="f53e6-118">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="f53e6-118">Any other pointer type</span></span>|  
|<span data-ttu-id="f53e6-119">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="f53e6-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="f53e6-120">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="f53e6-120">Any pointer type</span></span>|  
|<span data-ttu-id="f53e6-121">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="f53e6-121">Any pointer type</span></span>|<span data-ttu-id="f53e6-122">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="f53e6-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f53e6-123">Пример</span><span class="sxs-lookup"><span data-stu-id="f53e6-123">Example</span></span>  
 <span data-ttu-id="f53e6-124">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="f53e6-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="f53e6-125">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="f53e6-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="f53e6-126">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="f53e6-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f53e6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f53e6-127">See also</span></span>

- [<span data-ttu-id="f53e6-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f53e6-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f53e6-129">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="f53e6-129">Pointer types</span></span>](./pointer-types.md)
- [<span data-ttu-id="f53e6-130">Типы</span><span class="sxs-lookup"><span data-stu-id="f53e6-130">Types</span></span>](/dotnet/csharp/language-reference/keywords)
- [<span data-ttu-id="f53e6-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="f53e6-131">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="f53e6-132">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="f53e6-132">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="f53e6-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="f53e6-133">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
