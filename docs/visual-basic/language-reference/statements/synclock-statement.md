---
title: Оператор SyncLock (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: a2bd6ca11072113d8acff78032c19d48c30933c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615124"
---
# <a name="synclock-statement"></a><span data-ttu-id="2eb46-102">Оператор SyncLock</span><span class="sxs-lookup"><span data-stu-id="2eb46-102">SyncLock Statement</span></span>
<span data-ttu-id="2eb46-103">Применяет монопольную блокировку для блока инструкций, перед выполнением блока.</span><span class="sxs-lookup"><span data-stu-id="2eb46-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eb46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2eb46-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="2eb46-105">Части</span><span class="sxs-lookup"><span data-stu-id="2eb46-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="2eb46-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2eb46-106">Required.</span></span> <span data-ttu-id="2eb46-107">Выражение, возвращающее ссылку на объект.</span><span class="sxs-lookup"><span data-stu-id="2eb46-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="2eb46-108">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="2eb46-108">Optional.</span></span> <span data-ttu-id="2eb46-109">Блок операторов, которые должны выполняться, когда блокировка получена.</span><span class="sxs-lookup"><span data-stu-id="2eb46-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="2eb46-110">Завершает `SyncLock` блока.</span><span class="sxs-lookup"><span data-stu-id="2eb46-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2eb46-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="2eb46-111">Remarks</span></span>  
 <span data-ttu-id="2eb46-112">`SyncLock` Оператор гарантирует, что несколько потоков не выполняют блок операторов одновременно.</span><span class="sxs-lookup"><span data-stu-id="2eb46-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="2eb46-113">`SyncLock` запрещает каждому потоку входе в блок, пока не выполняется ни один поток.</span><span class="sxs-lookup"><span data-stu-id="2eb46-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="2eb46-114">Наиболее распространенное использование `SyncLock` предназначены для защиты данных не будет обновляться одновременно более чем одним потоком.</span><span class="sxs-lookup"><span data-stu-id="2eb46-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="2eb46-115">Если операторы для работы с данными необходимо перейти к завершению работы без прерывания, поместите их внутри `SyncLock` блока.</span><span class="sxs-lookup"><span data-stu-id="2eb46-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="2eb46-116">Блок операторов, защищенный монопольной блокировкой иногда называют *критический раздел*.</span><span class="sxs-lookup"><span data-stu-id="2eb46-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="2eb46-117">Правила</span><span class="sxs-lookup"><span data-stu-id="2eb46-117">Rules</span></span>  
  
- <span data-ttu-id="2eb46-118">Ветвление.</span><span class="sxs-lookup"><span data-stu-id="2eb46-118">Branching.</span></span> <span data-ttu-id="2eb46-119">Нельзя осуществлять ветвление в `SyncLock` заблокировать вне блока.</span><span class="sxs-lookup"><span data-stu-id="2eb46-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
- <span data-ttu-id="2eb46-120">Значение объекта блокировки.</span><span class="sxs-lookup"><span data-stu-id="2eb46-120">Lock Object Value.</span></span> <span data-ttu-id="2eb46-121">Значение `lockobject` не может быть `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="2eb46-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="2eb46-122">Необходимо создать объект блокировки, прежде чем использовать его в `SyncLock` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2eb46-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="2eb46-123">Не удается изменить значение `lockobject` при выполнении `SyncLock` блока.</span><span class="sxs-lookup"><span data-stu-id="2eb46-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="2eb46-124">Механизм требует, что объект блокировки остаются неизменными.</span><span class="sxs-lookup"><span data-stu-id="2eb46-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
- <span data-ttu-id="2eb46-125">Нельзя использовать [Await](../../../visual-basic/language-reference/operators/await-operator.md) оператор в `SyncLock` блока.</span><span class="sxs-lookup"><span data-stu-id="2eb46-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="2eb46-126">Поведение</span><span class="sxs-lookup"><span data-stu-id="2eb46-126">Behavior</span></span>  
  
- <span data-ttu-id="2eb46-127">Механизм.</span><span class="sxs-lookup"><span data-stu-id="2eb46-127">Mechanism.</span></span> <span data-ttu-id="2eb46-128">Когда поток достигает `SyncLock` инструкции, она оценивает `lockobject` выражение и приостанавливает выполнение, пока не получит монопольную блокировку для объекта, возвращаемого выражением.</span><span class="sxs-lookup"><span data-stu-id="2eb46-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="2eb46-129">Когда другой поток достигает `SyncLock` инструкции, она не использовать блокировку пока первый поток выполняет `End SyncLock` инструкции.</span><span class="sxs-lookup"><span data-stu-id="2eb46-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
- <span data-ttu-id="2eb46-130">Защищенные данные.</span><span class="sxs-lookup"><span data-stu-id="2eb46-130">Protected Data.</span></span> <span data-ttu-id="2eb46-131">Если `lockobject` — `Shared` переменных, монопольная блокировка предотвращает поток в любом экземпляре класса выполнение `SyncLock` блокировать во время его выполнения любого другого потока.</span><span class="sxs-lookup"><span data-stu-id="2eb46-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="2eb46-132">Это обеспечивает защиту данных, которая является общей для всех экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2eb46-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="2eb46-133">Если `lockobject` является переменной экземпляра (не `Shared`), Блокировка предотвращает одновременное выполнение потока в текущем экземпляре выполнения `SyncLock` блока, в то же время как другой поток, в том же экземпляре.</span><span class="sxs-lookup"><span data-stu-id="2eb46-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="2eb46-134">Это обеспечивает защиту данных, содержащихся в отдельном экземпляре.</span><span class="sxs-lookup"><span data-stu-id="2eb46-134">This protects data maintained by the individual instance.</span></span>  
  
- <span data-ttu-id="2eb46-135">Получение и выпуск.</span><span class="sxs-lookup"><span data-stu-id="2eb46-135">Acquisition and Release.</span></span> <span data-ttu-id="2eb46-136">Объект `SyncLock` блок ведет себя как `Try...Finally` построения, в котором `Try` блок применяет монопольную блокировку на `lockobject` и `Finally` блок освобождает его.</span><span class="sxs-lookup"><span data-stu-id="2eb46-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="2eb46-137">По этой причине `SyncLock` блок гарантирует освобождение блокировки, независимо от того, как выйти из блока.</span><span class="sxs-lookup"><span data-stu-id="2eb46-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="2eb46-138">Это справедливо даже в случае необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="2eb46-138">This is true even in the case of an unhandled exception.</span></span>  
  
- <span data-ttu-id="2eb46-139">Платформа вызывает функцию.</span><span class="sxs-lookup"><span data-stu-id="2eb46-139">Framework Calls.</span></span> <span data-ttu-id="2eb46-140">`SyncLock` Блок получает и освобождает монопольную блокировку, вызывая `Enter` и `Exit` методы `Monitor` в класс <xref:System.Threading> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2eb46-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="2eb46-141">Примеры программирования</span><span class="sxs-lookup"><span data-stu-id="2eb46-141">Programming Practices</span></span>  
 <span data-ttu-id="2eb46-142">`lockobject` Выражение всегда следует проверять на объект, к которому относится исключительно к классу.</span><span class="sxs-lookup"><span data-stu-id="2eb46-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="2eb46-143">Следует объявлять `Private` объектной переменной, чтобы защитить данные, относящиеся к текущим экземпляром, или `Private Shared` объектной переменной, чтобы защитить данные, общие для всех экземпляров.</span><span class="sxs-lookup"><span data-stu-id="2eb46-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="2eb46-144">Не следует использовать `Me` ключевое слово для предоставления блокировки для экземпляра объекта данных.</span><span class="sxs-lookup"><span data-stu-id="2eb46-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="2eb46-145">Если код, внешним по отношению к классу имеет ссылку на экземпляр вашего класса, он может использовать эту ссылку, как объект блокировки для `SyncLock` блок полностью отличаться от впечатления разработчика, защиты данных.</span><span class="sxs-lookup"><span data-stu-id="2eb46-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="2eb46-146">Таким образом, класс и другой класс может заблокировать друг с другом выполнение их несвязанных `SyncLock` блоков.</span><span class="sxs-lookup"><span data-stu-id="2eb46-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="2eb46-147">Аналогичным образом, блокировка строки может вызывать затруднения, так как любой другой код в процесс, использующий ту же строку будет совместно использовать ту же блокировку.</span><span class="sxs-lookup"><span data-stu-id="2eb46-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="2eb46-148">Также не следует использовать `Me.GetType` метод, чтобы предоставить объект блокировки для общих данных.</span><span class="sxs-lookup"><span data-stu-id="2eb46-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="2eb46-149">Это обусловлено `GetType` всегда возвращает тот же `Type` объект для заданного имени класса.</span><span class="sxs-lookup"><span data-stu-id="2eb46-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="2eb46-150">Внешний код может осуществлять вызов `GetType` в классе и получить тот же объект блокировки, которые вы используете.</span><span class="sxs-lookup"><span data-stu-id="2eb46-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="2eb46-151">Это может привести в обоих классах блокировки друг с другом и с их `SyncLock` блоков.</span><span class="sxs-lookup"><span data-stu-id="2eb46-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2eb46-152">Примеры</span><span class="sxs-lookup"><span data-stu-id="2eb46-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="2eb46-153">Описание</span><span class="sxs-lookup"><span data-stu-id="2eb46-153">Description</span></span>  
 <span data-ttu-id="2eb46-154">В следующем примере класс, который поддерживает простой список сообщений.</span><span class="sxs-lookup"><span data-stu-id="2eb46-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="2eb46-155">Сообщения хранятся в массиве, а последний элемент этого массива в переменной.</span><span class="sxs-lookup"><span data-stu-id="2eb46-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="2eb46-156">`addAnotherMessage` Процедура увеличивает значение последнего элемента и сохраняет новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="2eb46-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="2eb46-157">Эти две операции защищены с помощью `SyncLock` и `End SyncLock` инструкции, так как после последнего элемента был увеличен, должен храниться новое сообщение, прежде, чем любой другой поток может снова увеличить последнего элемента.</span><span class="sxs-lookup"><span data-stu-id="2eb46-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="2eb46-158">Если `simpleMessageList` один список сообщений для всех его экземпляров, переменные общих классов `messagesList` и `messagesLast` должна быть объявлена как `Shared`.</span><span class="sxs-lookup"><span data-stu-id="2eb46-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="2eb46-159">В данном случае переменная `messagesLock` также должен быть `Shared`, таким образом, чтобы могла быть объект блокировки, используемые каждым экземпляром.</span><span class="sxs-lookup"><span data-stu-id="2eb46-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2eb46-160">Код</span><span class="sxs-lookup"><span data-stu-id="2eb46-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="2eb46-161">Описание</span><span class="sxs-lookup"><span data-stu-id="2eb46-161">Description</span></span>  
 <span data-ttu-id="2eb46-162">В следующем примере используются потоки и `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="2eb46-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="2eb46-163">Поскольку `SyncLock` присутствует оператор, блокировка оператора является критической секции и `balance` никогда не будет отрицательным числом.</span><span class="sxs-lookup"><span data-stu-id="2eb46-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="2eb46-164">Вы можете закомментировать `SyncLock` и `End SyncLock` инструкции, чтобы увидеть эффект пропускают `SyncLock` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="2eb46-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2eb46-165">Код</span><span class="sxs-lookup"><span data-stu-id="2eb46-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="2eb46-166">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2eb46-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb46-167">См. также</span><span class="sxs-lookup"><span data-stu-id="2eb46-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="2eb46-168">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="2eb46-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
