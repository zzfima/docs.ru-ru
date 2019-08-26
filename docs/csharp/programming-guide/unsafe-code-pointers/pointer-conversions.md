---
title: Руководство по программированию на C#. Преобразования указателей
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 81b2110e6a571e174693fd272d1c6b4bf44dbae3
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588215"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="2a952-102">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="2a952-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="2a952-103">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="2a952-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="2a952-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="2a952-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="2a952-105">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="2a952-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="2a952-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="2a952-106">From</span></span>|<span data-ttu-id="2a952-107">Кому</span><span class="sxs-lookup"><span data-stu-id="2a952-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="2a952-108">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="2a952-108">Any pointer type</span></span>|<span data-ttu-id="2a952-109">void\*</span><span class="sxs-lookup"><span data-stu-id="2a952-109">void\*</span></span>|  
|<span data-ttu-id="2a952-110">null</span><span class="sxs-lookup"><span data-stu-id="2a952-110">null</span></span>|<span data-ttu-id="2a952-111">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="2a952-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="2a952-112">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="2a952-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="2a952-113">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2a952-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="2a952-114">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="2a952-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="2a952-115">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="2a952-115">From</span></span>|<span data-ttu-id="2a952-116">Кому</span><span class="sxs-lookup"><span data-stu-id="2a952-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="2a952-117">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="2a952-117">Any pointer type</span></span>|<span data-ttu-id="2a952-118">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="2a952-118">Any other pointer type</span></span>|  
|<span data-ttu-id="2a952-119">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="2a952-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="2a952-120">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="2a952-120">Any pointer type</span></span>|  
|<span data-ttu-id="2a952-121">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="2a952-121">Any pointer type</span></span>|<span data-ttu-id="2a952-122">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="2a952-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2a952-123">Пример</span><span class="sxs-lookup"><span data-stu-id="2a952-123">Example</span></span>  
 <span data-ttu-id="2a952-124">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="2a952-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="2a952-125">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="2a952-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="2a952-126">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="2a952-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2a952-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2a952-127">See also</span></span>

- [<span data-ttu-id="2a952-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="2a952-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2a952-129">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="2a952-129">Pointer types</span></span>](./pointer-types.md)
- [<span data-ttu-id="2a952-130">Типы</span><span class="sxs-lookup"><span data-stu-id="2a952-130">Types</span></span>](../../language-reference/keywords/types.md)
- [<span data-ttu-id="2a952-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="2a952-131">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="2a952-132">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="2a952-132">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="2a952-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="2a952-133">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
