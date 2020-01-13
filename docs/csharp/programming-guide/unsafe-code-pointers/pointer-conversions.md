---
title: Руководство по программированию на C#. Преобразования указателей
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 308d5e0646eeb94012dbe18d46d6d33f67dfeaf5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75698369"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="56834-102">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="56834-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="56834-103">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="56834-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="56834-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="56834-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="56834-105">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="56834-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="56834-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="56834-106">From</span></span>|<span data-ttu-id="56834-107">Кому</span><span class="sxs-lookup"><span data-stu-id="56834-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="56834-108">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="56834-108">Any pointer type</span></span>|<span data-ttu-id="56834-109">void\*</span><span class="sxs-lookup"><span data-stu-id="56834-109">void\*</span></span>|  
|<span data-ttu-id="56834-110">null</span><span class="sxs-lookup"><span data-stu-id="56834-110">null</span></span>|<span data-ttu-id="56834-111">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="56834-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="56834-112">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="56834-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="56834-113">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="56834-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="56834-114">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="56834-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="56834-115">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="56834-115">From</span></span>|<span data-ttu-id="56834-116">Кому</span><span class="sxs-lookup"><span data-stu-id="56834-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="56834-117">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="56834-117">Any pointer type</span></span>|<span data-ttu-id="56834-118">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="56834-118">Any other pointer type</span></span>|  
|<span data-ttu-id="56834-119">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="56834-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="56834-120">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="56834-120">Any pointer type</span></span>|  
|<span data-ttu-id="56834-121">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="56834-121">Any pointer type</span></span>|<span data-ttu-id="56834-122">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="56834-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="56834-123">Пример</span><span class="sxs-lookup"><span data-stu-id="56834-123">Example</span></span>  
 <span data-ttu-id="56834-124">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="56834-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="56834-125">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="56834-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="56834-126">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="56834-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="56834-127">См. также</span><span class="sxs-lookup"><span data-stu-id="56834-127">See also</span></span>

- [<span data-ttu-id="56834-128">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="56834-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="56834-129">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="56834-129">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="56834-130">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="56834-130">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="56834-131">Типы значений</span><span class="sxs-lookup"><span data-stu-id="56834-131">Value types</span></span>](../../language-reference/keywords/value-types.md)
- [<span data-ttu-id="56834-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="56834-132">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="56834-133">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="56834-133">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="56834-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="56834-134">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
