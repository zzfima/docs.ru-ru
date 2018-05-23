---
title: Преобразования указателей (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: e0c3a409d76468a6e214a96e8bb326a9d906fe18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="a4e28-102">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a4e28-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="a4e28-103">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="a4e28-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="a4e28-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="a4e28-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="a4e28-105">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="a4e28-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="a4e28-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="a4e28-106">From</span></span>|<span data-ttu-id="a4e28-107">Кому</span><span class="sxs-lookup"><span data-stu-id="a4e28-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="a4e28-108">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="a4e28-108">Any pointer type</span></span>|<span data-ttu-id="a4e28-109">void\*</span><span class="sxs-lookup"><span data-stu-id="a4e28-109">void\*</span></span>|  
|<span data-ttu-id="a4e28-110">null</span><span class="sxs-lookup"><span data-stu-id="a4e28-110">null</span></span>|<span data-ttu-id="a4e28-111">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="a4e28-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="a4e28-112">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="a4e28-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="a4e28-113">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a4e28-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="a4e28-114">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="a4e28-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="a4e28-115">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="a4e28-115">From</span></span>|<span data-ttu-id="a4e28-116">Кому</span><span class="sxs-lookup"><span data-stu-id="a4e28-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="a4e28-117">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="a4e28-117">Any pointer type</span></span>|<span data-ttu-id="a4e28-118">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="a4e28-118">Any other pointer type</span></span>|  
|<span data-ttu-id="a4e28-119">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="a4e28-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="a4e28-120">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="a4e28-120">Any pointer type</span></span>|  
|<span data-ttu-id="a4e28-121">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="a4e28-121">Any pointer type</span></span>|<span data-ttu-id="a4e28-122">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="a4e28-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a4e28-123">Пример</span><span class="sxs-lookup"><span data-stu-id="a4e28-123">Example</span></span>  
 <span data-ttu-id="a4e28-124">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="a4e28-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="a4e28-125">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="a4e28-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="a4e28-126">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="a4e28-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a4e28-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a4e28-127">See Also</span></span>  
 [<span data-ttu-id="a4e28-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a4e28-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a4e28-129">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="a4e28-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="a4e28-130">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="a4e28-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="a4e28-131">Типы</span><span class="sxs-lookup"><span data-stu-id="a4e28-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="a4e28-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="a4e28-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="a4e28-133">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="a4e28-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="a4e28-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="a4e28-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
