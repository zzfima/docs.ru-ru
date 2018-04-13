---
title: '* Оператор (ссылка C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 64c32def0935f4347f9aaccc2865b9cd33dd8a70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="60462-102">Оператор \* (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="60462-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="60462-103">Оператор умножения (`*`), который вычисляет произведение двух операндов.</span><span class="sxs-lookup"><span data-stu-id="60462-103">The multiplication operator (`*`), which computes the product of its operands.</span></span>  <span data-ttu-id="60462-104">Кроме того, это оператор разыменования, позволяющий выполнять чтение и запись в указателе.</span><span class="sxs-lookup"><span data-stu-id="60462-104">Also, the dereference operator, which allows reading and writing to a pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60462-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="60462-105">Remarks</span></span>  
 <span data-ttu-id="60462-106">Все числовые типы имеют предопределенные операторы умножения.</span><span class="sxs-lookup"><span data-stu-id="60462-106">All numeric types have predefined multiplication operators.</span></span>  
  
 <span data-ttu-id="60462-107">Оператор `*` также используется для объявления типов указателей и для разыменования указателей.</span><span class="sxs-lookup"><span data-stu-id="60462-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="60462-108">Этот оператор может использоваться только в небезопасных контекстах, обозначенных с помощью ключевого слова [unsafe](../../../csharp/language-reference/keywords/unsafe.md) и требующих параметр компилятора [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="60462-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="60462-109">Оператор разыменования также известен как оператор косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="60462-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="60462-110">Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `*` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .</span><span class="sxs-lookup"><span data-stu-id="60462-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="60462-111">При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.</span><span class="sxs-lookup"><span data-stu-id="60462-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60462-112">Пример</span><span class="sxs-lookup"><span data-stu-id="60462-112">Example</span></span>  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="60462-113">Пример</span><span class="sxs-lookup"><span data-stu-id="60462-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="60462-114">См. также</span><span class="sxs-lookup"><span data-stu-id="60462-114">See Also</span></span>  
 [<span data-ttu-id="60462-115">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="60462-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="60462-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="60462-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="60462-117">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="60462-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="60462-118">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="60462-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
