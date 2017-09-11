---
title: "Преобразования указателей (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e415d892d979e2bdcd648256150e2a96b1772ce4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="d32ab-102">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d32ab-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="d32ab-103">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="d32ab-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="d32ab-104">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="d32ab-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="d32ab-105">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="d32ab-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="d32ab-106">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="d32ab-106">From</span></span>|<span data-ttu-id="d32ab-107">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="d32ab-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="d32ab-108">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d32ab-108">Any pointer type</span></span>|<span data-ttu-id="d32ab-109">void*</span><span class="sxs-lookup"><span data-stu-id="d32ab-109">void*</span></span>|  
|<span data-ttu-id="d32ab-110">null</span><span class="sxs-lookup"><span data-stu-id="d32ab-110">null</span></span>|<span data-ttu-id="d32ab-111">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d32ab-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="d32ab-112">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="d32ab-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="d32ab-113">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d32ab-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="d32ab-114">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="d32ab-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="d32ab-115">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="d32ab-115">From</span></span>|<span data-ttu-id="d32ab-116">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="d32ab-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="d32ab-117">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d32ab-117">Any pointer type</span></span>|<span data-ttu-id="d32ab-118">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d32ab-118">Any other pointer type</span></span>|  
|<span data-ttu-id="d32ab-119">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="d32ab-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="d32ab-120">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d32ab-120">Any pointer type</span></span>|  
|<span data-ttu-id="d32ab-121">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d32ab-121">Any pointer type</span></span>|<span data-ttu-id="d32ab-122">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="d32ab-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d32ab-123">Пример</span><span class="sxs-lookup"><span data-stu-id="d32ab-123">Example</span></span>  
 <span data-ttu-id="d32ab-124">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="d32ab-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="d32ab-125">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="d32ab-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="d32ab-126">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="d32ab-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 <span data-ttu-id="d32ab-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d32ab-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span></span>  
  
 <span data-ttu-id="d32ab-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d32ab-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32ab-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d32ab-129">See Also</span></span>  
 <span data-ttu-id="d32ab-130">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d32ab-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d32ab-131">[Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="d32ab-131">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="d32ab-132">[Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="d32ab-132">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="d32ab-133">[Типы](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="d32ab-133">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="d32ab-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="d32ab-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="d32ab-135">[Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d32ab-135">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="d32ab-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="d32ab-136">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

