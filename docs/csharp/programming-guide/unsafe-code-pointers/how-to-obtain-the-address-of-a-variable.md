---
title: "Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="ebc0e-102">Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ebc0e-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="ebc0e-103">Чтобы получить адрес унарного выражения, при вычислении которого получается фиксированная переменная, используйте оператор address-of:</span><span class="sxs-lookup"><span data-stu-id="ebc0e-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="ebc0e-104">Оператор address-of применяется только к переменным.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="ebc0e-105">Если переменная может перемещаться, используйте [оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md), чтобы временно зафиксировать переменную перед получением ее адреса.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="ebc0e-106">Вам необходимо самостоятельно обеспечить проверку того, что переменная инициализирована.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="ebc0e-107">Если переменная не инициализирована, компилятор не выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="ebc0e-108">Получить адрес константы или значения нельзя.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebc0e-109">Пример</span><span class="sxs-lookup"><span data-stu-id="ebc0e-109">Example</span></span>  
 <span data-ttu-id="ebc0e-110">В этом примере объявляется указатель на `int`, `p`, которому присваивается адрес целочисленной переменной `number`.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="ebc0e-111">Переменная `number` инициализируется в результате присваивания *p.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="ebc0e-112">Если закомментировать этот оператор присваивания, инициализация `number` будет удалена, однако во время компиляции ошибка не возникнет.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="ebc0e-113">Обратите внимание на использование оператора [доступа к члену](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) (`->`) для получения и отображения адреса, хранящегося в указателе.</span><span class="sxs-lookup"><span data-stu-id="ebc0e-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ebc0e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ebc0e-114">See Also</span></span>  
 [<span data-ttu-id="ebc0e-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ebc0e-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ebc0e-116">Выражения указателей</span><span class="sxs-lookup"><span data-stu-id="ebc0e-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="ebc0e-117">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="ebc0e-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="ebc0e-118">Типы</span><span class="sxs-lookup"><span data-stu-id="ebc0e-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="ebc0e-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="ebc0e-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="ebc0e-120">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="ebc0e-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="ebc0e-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="ebc0e-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
