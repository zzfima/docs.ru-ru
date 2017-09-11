---
title: "Практическое руководство. Получение значения переменной указателя (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
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
ms.openlocfilehash: 4cff42de07f2edb279ddd1cafefe9f4b67a38ce1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="666cd-102">Практическое руководство. Получение значения переменной указателя (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="666cd-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="666cd-103">Оператор косвенного обращения к указателю позволяет получить переменную в расположении, на которое указывает указатель.</span><span class="sxs-lookup"><span data-stu-id="666cd-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="666cd-104">Выражение имеет следующую форму, где `p` — это тип указателя:</span><span class="sxs-lookup"><span data-stu-id="666cd-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="666cd-105">Унарный оператор косвенного обращения можно использовать только по отношению к выражениям с типом указателя.</span><span class="sxs-lookup"><span data-stu-id="666cd-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="666cd-106">Кроме того, его нельзя применять к указателю [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="666cd-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="666cd-107">Если оператор косвенного обращения применяется к указателю [NULL](../../../csharp/language-reference/keywords/null.md), результат будет зависеть от особенностей реализации.</span><span class="sxs-lookup"><span data-stu-id="666cd-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="666cd-108">Пример</span><span class="sxs-lookup"><span data-stu-id="666cd-108">Example</span></span>  
 <span data-ttu-id="666cd-109">В следующем примере доступ к переменной типа `char` осуществляется с использованием указателей разных типов.</span><span class="sxs-lookup"><span data-stu-id="666cd-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="666cd-110">Обратите внимание, что адрес `theChar` может изменяться с каждым запуском из-за изменения физического адреса переменной.</span><span class="sxs-lookup"><span data-stu-id="666cd-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 <span data-ttu-id="666cd-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="666cd-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="666cd-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="666cd-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span></span>  
  
 <span data-ttu-id="666cd-113">**Значение theChar = Z** </span><span class="sxs-lookup"><span data-stu-id="666cd-113">**Value of theChar = Z** </span></span>  
<span data-ttu-id="666cd-114">**Адрес theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="666cd-114">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="666cd-115">**Значение pChar = Z** </span><span class="sxs-lookup"><span data-stu-id="666cd-115">**Value of pChar = Z** </span></span>  
<span data-ttu-id="666cd-116">**Значение pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="666cd-116">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="666cd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="666cd-117">See Also</span></span>  
 <span data-ttu-id="666cd-118">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="666cd-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="666cd-119">[Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="666cd-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="666cd-120">[Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="666cd-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="666cd-121">[Типы](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="666cd-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="666cd-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="666cd-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="666cd-123">[Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="666cd-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="666cd-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="666cd-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

