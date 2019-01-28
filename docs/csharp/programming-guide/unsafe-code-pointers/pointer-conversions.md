---
title: Руководство по программированию на C#. Преобразования указателей
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 8fa1c1442d146c9d2fbdb2fa969b2e29d7ef765d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498311"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="3bd9d-102">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="3bd9d-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="3bd9d-103">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="3bd9d-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="3bd9d-105">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="3bd9d-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="3bd9d-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="3bd9d-106">From</span></span>|<span data-ttu-id="3bd9d-107">Кому</span><span class="sxs-lookup"><span data-stu-id="3bd9d-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="3bd9d-108">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="3bd9d-108">Any pointer type</span></span>|<span data-ttu-id="3bd9d-109">void\*</span><span class="sxs-lookup"><span data-stu-id="3bd9d-109">void\*</span></span>|  
|<span data-ttu-id="3bd9d-110">null</span><span class="sxs-lookup"><span data-stu-id="3bd9d-110">null</span></span>|<span data-ttu-id="3bd9d-111">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="3bd9d-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="3bd9d-112">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="3bd9d-113">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="3bd9d-114">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="3bd9d-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="3bd9d-115">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="3bd9d-115">From</span></span>|<span data-ttu-id="3bd9d-116">Кому</span><span class="sxs-lookup"><span data-stu-id="3bd9d-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="3bd9d-117">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="3bd9d-117">Any pointer type</span></span>|<span data-ttu-id="3bd9d-118">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="3bd9d-118">Any other pointer type</span></span>|  
|<span data-ttu-id="3bd9d-119">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="3bd9d-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="3bd9d-120">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="3bd9d-120">Any pointer type</span></span>|  
|<span data-ttu-id="3bd9d-121">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="3bd9d-121">Any pointer type</span></span>|<span data-ttu-id="3bd9d-122">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="3bd9d-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3bd9d-123">Пример</span><span class="sxs-lookup"><span data-stu-id="3bd9d-123">Example</span></span>  
 <span data-ttu-id="3bd9d-124">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="3bd9d-125">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="3bd9d-126">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="3bd9d-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3bd9d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3bd9d-127">See also</span></span>

- [<span data-ttu-id="3bd9d-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3bd9d-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3bd9d-129">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="3bd9d-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="3bd9d-130">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="3bd9d-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="3bd9d-131">Типы</span><span class="sxs-lookup"><span data-stu-id="3bd9d-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="3bd9d-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="3bd9d-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="3bd9d-133">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="3bd9d-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="3bd9d-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="3bd9d-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
