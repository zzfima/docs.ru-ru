---
title: Рекурсивные процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: 0bb89ac855d65d7677a062346db8665698dbb805
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514346"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="a7c81-102">Рекурсивные процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7c81-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="a7c81-103">Объект *рекурсивного* процедуры — это приложения, вызывает саму себя.</span><span class="sxs-lookup"><span data-stu-id="a7c81-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="a7c81-104">Как правило это не самый эффективный способ написания кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a7c81-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="a7c81-105">Следующая процедура использует рекурсию для вычисления факториала исходного аргумента.</span><span class="sxs-lookup"><span data-stu-id="a7c81-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="a7c81-106">Вопросы, связанные с рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="a7c81-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="a7c81-107">**Ограничивающие условия**.</span><span class="sxs-lookup"><span data-stu-id="a7c81-107">**Limiting Conditions**.</span></span> <span data-ttu-id="a7c81-108">Необходимо разработать рекурсивную процедуру для проверки по крайней мере одно условие, можно прервать рекурсию, и вы также должны обрабатывать случаи, когда такое условие не выполняется в течение разумное число рекурсивных вызовов.</span><span class="sxs-lookup"><span data-stu-id="a7c81-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="a7c81-109">Без хотя бы одно условие, которое может быть выполнено без ошибок процедура выполняется высокий риск выполнения в бесконечный цикл.</span><span class="sxs-lookup"><span data-stu-id="a7c81-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="a7c81-110">**Использование памяти**.</span><span class="sxs-lookup"><span data-stu-id="a7c81-110">**Memory Usage**.</span></span> <span data-ttu-id="a7c81-111">Приложение имеет ограниченный объем пространства для локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="a7c81-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="a7c81-112">Каждый раз, процедура вызывает саму себя, она использует больше этого пространства для дополнительных копий ее локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="a7c81-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="a7c81-113">Если этот процесс продолжается неопределенное время, она в конечном итоге вызовет <xref:System.StackOverflowException> ошибки.</span><span class="sxs-lookup"><span data-stu-id="a7c81-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="a7c81-114">**Эффективность**.</span><span class="sxs-lookup"><span data-stu-id="a7c81-114">**Efficiency**.</span></span> <span data-ttu-id="a7c81-115">Почти всегда можно заменить цикл для рекурсии.</span><span class="sxs-lookup"><span data-stu-id="a7c81-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="a7c81-116">Цикл не издержки передача аргументов, инициализации дополнительного хранилища и возврат значений.</span><span class="sxs-lookup"><span data-stu-id="a7c81-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="a7c81-117">Производительность может быть гораздо выше без рекурсивных вызовов.</span><span class="sxs-lookup"><span data-stu-id="a7c81-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="a7c81-118">**Взаимная рекурсия**.</span><span class="sxs-lookup"><span data-stu-id="a7c81-118">**Mutual Recursion**.</span></span> <span data-ttu-id="a7c81-119">Можно заметить очень низкую производительность или даже бесконечный цикл, если две процедуры вызывают друг друга.</span><span class="sxs-lookup"><span data-stu-id="a7c81-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="a7c81-120">Такая архитектура представляет те же проблемы, как одной рекурсивной процедуры, но может быть сложнее обнаружить и устранить.</span><span class="sxs-lookup"><span data-stu-id="a7c81-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="a7c81-121">**Вызов со скобками**.</span><span class="sxs-lookup"><span data-stu-id="a7c81-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="a7c81-122">Когда `Function` процедура вызывает саму себя рекурсивно, следует выполнить процедуры имя со скобками, даже если отсутствует список аргументов.</span><span class="sxs-lookup"><span data-stu-id="a7c81-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="a7c81-123">В противном случае извлекается имя функции, представляющего возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="a7c81-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="a7c81-124">**Тестирование**.</span><span class="sxs-lookup"><span data-stu-id="a7c81-124">**Testing**.</span></span> <span data-ttu-id="a7c81-125">Если вы пишете рекурсивную процедуру, вы должны проверить его очень осторожно убедитесь в том, что он всегда соответствует некоторым условиям ограничивающим.</span><span class="sxs-lookup"><span data-stu-id="a7c81-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="a7c81-126">Следует также убедиться, не хватает памяти из-за наличия слишком много рекурсивных вызовов.</span><span class="sxs-lookup"><span data-stu-id="a7c81-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c81-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a7c81-127">See Also</span></span>  
 <xref:System.StackOverflowException>  
 [<span data-ttu-id="a7c81-128">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a7c81-128">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="a7c81-129">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="a7c81-129">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="a7c81-130">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="a7c81-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="a7c81-131">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="a7c81-131">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="a7c81-132">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="a7c81-132">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="a7c81-133">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="a7c81-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="a7c81-134">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="a7c81-134">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="a7c81-135">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="a7c81-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="a7c81-136">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="a7c81-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="a7c81-137">Разрешение вопросов, связанных с исключениями: System.StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="a7c81-137">Troubleshooting Exceptions: System.StackOverflowException</span></span>](https://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
