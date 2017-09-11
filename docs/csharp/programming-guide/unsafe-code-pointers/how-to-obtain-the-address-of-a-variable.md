---
title: "Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
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
ms.openlocfilehash: 169f68cc80b7a27427a9987942e66e0ba9ed1a02
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="e83df-102">Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e83df-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="e83df-103">Чтобы получить адрес унарного выражения, при вычислении которого получается фиксированная переменная, используйте оператор address-of:</span><span class="sxs-lookup"><span data-stu-id="e83df-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="e83df-104">Оператор address-of применяется только к переменным.</span><span class="sxs-lookup"><span data-stu-id="e83df-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="e83df-105">Если переменная может перемещаться, используйте [оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md), чтобы временно зафиксировать переменную перед получением ее адреса.</span><span class="sxs-lookup"><span data-stu-id="e83df-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="e83df-106">Вам необходимо самостоятельно обеспечить проверку того, что переменная инициализирована.</span><span class="sxs-lookup"><span data-stu-id="e83df-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="e83df-107">Если переменная не инициализирована, компилятор не выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e83df-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="e83df-108">Получить адрес константы или значения нельзя.</span><span class="sxs-lookup"><span data-stu-id="e83df-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e83df-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e83df-109">Example</span></span>  
 <span data-ttu-id="e83df-110">В этом примере объявляется указатель на `int`, `p`, которому присваивается адрес целочисленной переменной `number`.</span><span class="sxs-lookup"><span data-stu-id="e83df-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="e83df-111">Переменная `number` инициализируется в результате присваивания *p.</span><span class="sxs-lookup"><span data-stu-id="e83df-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="e83df-112">Если закомментировать этот оператор присваивания, инициализация `number` будет удалена, однако во время компиляции ошибка не возникнет.</span><span class="sxs-lookup"><span data-stu-id="e83df-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="e83df-113">Обратите внимание на использование оператора [доступа к члену](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) (`->`) для получения и отображения адреса, хранящегося в указателе.</span><span class="sxs-lookup"><span data-stu-id="e83df-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 <span data-ttu-id="e83df-114">[!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e83df-114">[!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="e83df-115">[!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e83df-115">[!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e83df-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e83df-116">See Also</span></span>  
 <span data-ttu-id="e83df-117">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e83df-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e83df-118">[Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="e83df-118">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="e83df-119">[Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="e83df-119">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="e83df-120">[Типы](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="e83df-120">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="e83df-121">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="e83df-121">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="e83df-122">[Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e83df-122">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="e83df-123">stackalloc</span><span class="sxs-lookup"><span data-stu-id="e83df-123">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

