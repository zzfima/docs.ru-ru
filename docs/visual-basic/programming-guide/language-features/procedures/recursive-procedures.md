---
title: "Рекурсивные процедуры (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5e4838bb14125dcfd27798acf0c196f351ba5b90
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="6e6ca-102">Рекурсивные процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e6ca-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="6e6ca-103">Объект *рекурсивного* — процедура, которая вызывает сама себя.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="6e6ca-104">Как правило, это не самый эффективный способ написания [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] кода.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
 <span data-ttu-id="6e6ca-105">Следующая процедура использует рекурсию для вычисления факториала исходного аргумента.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 <span data-ttu-id="6e6ca-106">[!code-vb[VbVbcnProcedures&#51;](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="6e6ca-106">[!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span></span>  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="6e6ca-107">Вопросы, связанные с рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="6e6ca-107">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="6e6ca-108">**Ограничивающие условия**.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-108">**Limiting Conditions**.</span></span> <span data-ttu-id="6e6ca-109">Необходимо разработать рекурсивную процедуру для проверки по крайней мере одного условия, которое может прервать рекурсию, и вы также должны обрабатывать случаи, когда такое условие не выполняется в течение разумного числа рекурсивных вызовов.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-109">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="6e6ca-110">Без хотя бы одного условия, которое может быть выполнено без ошибок процедура выполняется высокий риск выполнения в бесконечном цикле.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-110">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="6e6ca-111">**Использование памяти**.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-111">**Memory Usage**.</span></span> <span data-ttu-id="6e6ca-112">Приложение имеет ограниченный объем пространства для локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-112">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="6e6ca-113">Каждый раз, когда процедура вызывает саму себя, используется больше этого пространства для дополнительных копий ее локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-113">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="6e6ca-114">Если этот процесс будет продолжаться неопределенно долго, он в конечном итоге вызовет <xref:System.StackOverflowException>ошибка.</xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="6e6ca-114">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="6e6ca-115">**Эффективность**.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-115">**Efficiency**.</span></span> <span data-ttu-id="6e6ca-116">Почти всегда можно заменить цикл для рекурсии.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-116">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="6e6ca-117">Цикл не имеет дополнительных издержек аргументов передачи, инициализации дополнительного хранилища и возврат значений.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-117">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="6e6ca-118">Производительность может быть гораздо выше без рекурсивного вызова.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-118">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="6e6ca-119">**Взаимная рекурсия**.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-119">**Mutual Recursion**.</span></span> <span data-ttu-id="6e6ca-120">Можно наблюдать очень низкую производительность или даже бесконечный цикл, если две процедуры вызывают друг друга.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-120">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="6e6ca-121">Такой макет представляет те же проблемы, как одна Рекурсивная процедура, но может быть сложнее обнаружить и отладить.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-121">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="6e6ca-122">**Вызов со скобками**.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-122">**Calling with Parentheses**.</span></span> <span data-ttu-id="6e6ca-123">Когда `Function` процедура вызывает себя рекурсивно, необходимо выполнить процедуру имя со скобками, даже если отсутствует список аргументов.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-123">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="6e6ca-124">В противном случае — берется имя функции, представляющего возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-124">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="6e6ca-125">**Тестирование**.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-125">**Testing**.</span></span> <span data-ttu-id="6e6ca-126">Если вы пишете рекурсивную процедуру, следует проверить ее очень внимательно, чтобы убедиться, что он всегда условие некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-126">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="6e6ca-127">Следует также убедиться, что не может работать не хватает памяти из-за слишком большим количеством рекурсивных вызовов.</span><span class="sxs-lookup"><span data-stu-id="6e6ca-127">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e6ca-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6e6ca-128">See Also</span></span>  
 <span data-ttu-id="6e6ca-129"><xref:System.StackOverflowException></xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="6e6ca-129"><xref:System.StackOverflowException></span></span>   
<span data-ttu-id="6e6ca-130"> [Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-130"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="6e6ca-131"> [Sub-процедуры](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-131"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="6e6ca-132"> [Процедуры функций](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-132"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="6e6ca-133"> [Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-133"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="6e6ca-134"> [Процедуры операторов](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-134"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="6e6ca-135"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-135"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="6e6ca-136"> [Перегрузка процедур](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="6e6ca-137"> [Рекомендации по устранению неполадок](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="6e6ca-138"> [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="6e6ca-138"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="6e6ca-139"> [Разрешение вопросов, связанных с исключениями: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span><span class="sxs-lookup"><span data-stu-id="6e6ca-139"> [Troubleshooting Exceptions: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span></span>
