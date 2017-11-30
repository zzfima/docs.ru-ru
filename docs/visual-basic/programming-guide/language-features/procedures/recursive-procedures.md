---
title: "Рекурсивные процедуры (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 444eeaf043cf3710c5154fd7e8577590e3ce7d1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="099aa-102">Рекурсивные процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="099aa-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="099aa-103">Объект *рекурсивные* процедура является тот, который вызывает саму себя.</span><span class="sxs-lookup"><span data-stu-id="099aa-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="099aa-104">Как правило, это не самый эффективный способ написания [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] кода.</span><span class="sxs-lookup"><span data-stu-id="099aa-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
 <span data-ttu-id="099aa-105">Следующая процедура использует рекурсию для вычисления факториала исходного аргумента.</span><span class="sxs-lookup"><span data-stu-id="099aa-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="099aa-106">Вопросы, связанные с рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="099aa-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="099aa-107">**Ограничивающие условия**.</span><span class="sxs-lookup"><span data-stu-id="099aa-107">**Limiting Conditions**.</span></span> <span data-ttu-id="099aa-108">Необходимо разработать рекурсивную процедуру для проверки на наличие хотя бы одного условия, которое может прервать рекурсию, и вы также должны обрабатывать случаи, когда такое условие не выполняется в течение разумного числа рекурсивных вызовов.</span><span class="sxs-lookup"><span data-stu-id="099aa-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="099aa-109">Без хотя бы одного условия, которое может быть выполнено без ошибок процедура выполняется высокий риск выполнения в бесконечный цикл.</span><span class="sxs-lookup"><span data-stu-id="099aa-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="099aa-110">**Использование памяти**.</span><span class="sxs-lookup"><span data-stu-id="099aa-110">**Memory Usage**.</span></span> <span data-ttu-id="099aa-111">Ваше приложение имеет ограниченный объем пространства для локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="099aa-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="099aa-112">Каждый раз, когда процедура вызывает саму себя, используется больше этого пространства для дополнительных копий ее локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="099aa-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="099aa-113">Если этот процесс будет продолжаться неопределенно долго, он в конечном итоге вызовет <xref:System.StackOverflowException> ошибки.</span><span class="sxs-lookup"><span data-stu-id="099aa-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="099aa-114">**Эффективность**.</span><span class="sxs-lookup"><span data-stu-id="099aa-114">**Efficiency**.</span></span> <span data-ttu-id="099aa-115">Почти всегда можно заменить цикл для рекурсии.</span><span class="sxs-lookup"><span data-stu-id="099aa-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="099aa-116">Цикл не имеет издержек аргументов передачи, инициализации дополнительного хранилища и возврат значений.</span><span class="sxs-lookup"><span data-stu-id="099aa-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="099aa-117">Производительность может быть гораздо выше без рекурсивного вызова.</span><span class="sxs-lookup"><span data-stu-id="099aa-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="099aa-118">**Взаимная рекурсия**.</span><span class="sxs-lookup"><span data-stu-id="099aa-118">**Mutual Recursion**.</span></span> <span data-ttu-id="099aa-119">Можно наблюдать очень низкую производительность или даже бесконечный цикл, если две процедуры вызывают друг друга.</span><span class="sxs-lookup"><span data-stu-id="099aa-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="099aa-120">Такая конструкция представляет те же проблемы, как одна Рекурсивная процедура, но может быть сложнее обнаружить и отладить.</span><span class="sxs-lookup"><span data-stu-id="099aa-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="099aa-121">**Вызов со скобками**.</span><span class="sxs-lookup"><span data-stu-id="099aa-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="099aa-122">Когда `Function` процедура вызывает саму себя рекурсивно, следует выполнить имя процедуры в скобки, даже если отсутствует список аргументов.</span><span class="sxs-lookup"><span data-stu-id="099aa-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="099aa-123">В противном случае имя функции воспринимается как представляющий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="099aa-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="099aa-124">**Тестирование**.</span><span class="sxs-lookup"><span data-stu-id="099aa-124">**Testing**.</span></span> <span data-ttu-id="099aa-125">При написании рекурсивную процедуру, необходимо проверить ее очень внимательно важно убедиться, что он всегда соответствует определенному условию ограничения.</span><span class="sxs-lookup"><span data-stu-id="099aa-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="099aa-126">Также следует убедиться, не хватает памяти из-за слишком большим количеством рекурсивных вызовов.</span><span class="sxs-lookup"><span data-stu-id="099aa-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099aa-127">См. также</span><span class="sxs-lookup"><span data-stu-id="099aa-127">See Also</span></span>  
 <xref:System.StackOverflowException>  
 [<span data-ttu-id="099aa-128">Процедуры</span><span class="sxs-lookup"><span data-stu-id="099aa-128">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="099aa-129">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="099aa-129">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="099aa-130">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="099aa-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="099aa-131">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="099aa-131">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="099aa-132">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="099aa-132">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="099aa-133">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="099aa-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="099aa-134">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="099aa-134">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="099aa-135">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="099aa-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="099aa-136">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="099aa-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="099aa-137">Разрешение вопросов, связанных с исключениями: System.StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="099aa-137">Troubleshooting Exceptions: System.StackOverflowException</span></span>](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
