---
title: Оператор SyncLock
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 0f430edce99513b0de9ef437d70648a128b336b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352807"
---
# <a name="synclock-statement"></a><span data-ttu-id="25114-102">Оператор SyncLock</span><span class="sxs-lookup"><span data-stu-id="25114-102">SyncLock Statement</span></span>
<span data-ttu-id="25114-103">Получает монопольную блокировку для блока операторов перед выполнением блока.</span><span class="sxs-lookup"><span data-stu-id="25114-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25114-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25114-104">Syntax</span></span>  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="25114-105">Части</span><span class="sxs-lookup"><span data-stu-id="25114-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="25114-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="25114-106">Required.</span></span> <span data-ttu-id="25114-107">Выражение, результатом которого является ссылка на объект.</span><span class="sxs-lookup"><span data-stu-id="25114-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="25114-108">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="25114-108">Optional.</span></span> <span data-ttu-id="25114-109">Блок инструкций, которые выполняются при получении блокировки.</span><span class="sxs-lookup"><span data-stu-id="25114-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="25114-110">Завершает блок `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25114-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="25114-111">Remarks</span></span>  
 <span data-ttu-id="25114-112">Оператор `SyncLock` гарантирует, что несколько потоков не выполняют блок инструкций одновременно.</span><span class="sxs-lookup"><span data-stu-id="25114-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="25114-113">`SyncLock` предотвращает вход каждого потока в блок до тех пор, пока не будет выполнен другой поток.</span><span class="sxs-lookup"><span data-stu-id="25114-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="25114-114">Чаще всего `SyncLock` используется для защиты данных от одновременного обновления более чем одним потоком.</span><span class="sxs-lookup"><span data-stu-id="25114-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="25114-115">Если инструкции, управляющие данными, должны переходить к завершению без прерывания, помещайте их в блок `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="25114-116">Блок операторов, защищенный монопольной блокировкой, иногда называют *критическим разделом*.</span><span class="sxs-lookup"><span data-stu-id="25114-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="25114-117">Правила</span><span class="sxs-lookup"><span data-stu-id="25114-117">Rules</span></span>  
  
- <span data-ttu-id="25114-118">Ветвления.</span><span class="sxs-lookup"><span data-stu-id="25114-118">Branching.</span></span> <span data-ttu-id="25114-119">Невозможно выполнить ветвление в блок `SyncLock`, находящийся за пределами блока.</span><span class="sxs-lookup"><span data-stu-id="25114-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
- <span data-ttu-id="25114-120">Блокировка значения объекта.</span><span class="sxs-lookup"><span data-stu-id="25114-120">Lock Object Value.</span></span> <span data-ttu-id="25114-121">Значение `lockobject` не может быть `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="25114-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="25114-122">Объект Lock необходимо создать до его использования в инструкции `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="25114-123">Невозможно изменить значение `lockobject` при выполнении блока `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="25114-124">Механизм требует, чтобы объект блокировки оставался без изменений.</span><span class="sxs-lookup"><span data-stu-id="25114-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
- <span data-ttu-id="25114-125">Оператор [await](../../../visual-basic/language-reference/operators/await-operator.md) нельзя использовать в блоке `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="25114-126">Поведение</span><span class="sxs-lookup"><span data-stu-id="25114-126">Behavior</span></span>  
  
- <span data-ttu-id="25114-127">Механизм.</span><span class="sxs-lookup"><span data-stu-id="25114-127">Mechanism.</span></span> <span data-ttu-id="25114-128">Когда поток достигает оператора `SyncLock`, он вычисляет выражение `lockobject` и приостанавливает выполнение до тех пор, пока не получит монопольную блокировку на объект, возвращенный выражением.</span><span class="sxs-lookup"><span data-stu-id="25114-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="25114-129">Когда другой поток достигает оператора `SyncLock`, он не получает блокировку до тех пор, пока первый поток не выполнит инструкцию `End SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
- <span data-ttu-id="25114-130">Защищенные данные.</span><span class="sxs-lookup"><span data-stu-id="25114-130">Protected Data.</span></span> <span data-ttu-id="25114-131">Если `lockobject` является `Shared` переменной, монопольная блокировка запрещает потоку в любом экземпляре класса выполнять блок `SyncLock`, пока он выполняется любым другим потоком.</span><span class="sxs-lookup"><span data-stu-id="25114-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="25114-132">Это защищает данные, которые являются общими для всех экземпляров.</span><span class="sxs-lookup"><span data-stu-id="25114-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="25114-133">Если `lockobject` является переменной экземпляра (не `Shared`), блокировка не дает потоку, запущенному в текущем экземпляре, выполнять блок `SyncLock` в то же время, что и другой поток в том же экземпляре.</span><span class="sxs-lookup"><span data-stu-id="25114-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="25114-134">Это защищает данные, обслуживаемые отдельным экземпляром.</span><span class="sxs-lookup"><span data-stu-id="25114-134">This protects data maintained by the individual instance.</span></span>  
  
- <span data-ttu-id="25114-135">Приобретение и выпуск.</span><span class="sxs-lookup"><span data-stu-id="25114-135">Acquisition and Release.</span></span> <span data-ttu-id="25114-136">Блок `SyncLock` ведет себя как конструкция `Try...Finally`, в которой блок `Try` получает монопольную блокировку на `lockobject`, а блок `Finally` освобождает ее.</span><span class="sxs-lookup"><span data-stu-id="25114-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="25114-137">По этой причине блок `SyncLock` гарантирует освобождение блокировки, независимо от того, как вы выйдете из блока.</span><span class="sxs-lookup"><span data-stu-id="25114-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="25114-138">Это справедливо даже в случае необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="25114-138">This is true even in the case of an unhandled exception.</span></span>  
  
- <span data-ttu-id="25114-139">Платформа вызывает.</span><span class="sxs-lookup"><span data-stu-id="25114-139">Framework Calls.</span></span> <span data-ttu-id="25114-140">Блок `SyncLock` получает и освобождает монопольную блокировку, вызывая методы `Enter` и `Exit` класса `Monitor` в пространстве имен <xref:System.Threading>.</span><span class="sxs-lookup"><span data-stu-id="25114-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="25114-141">Рекомендации по программированию</span><span class="sxs-lookup"><span data-stu-id="25114-141">Programming Practices</span></span>  
 <span data-ttu-id="25114-142">`lockobject`ное выражение всегда должно оцениваться как объект, который относится исключительно к вашему классу.</span><span class="sxs-lookup"><span data-stu-id="25114-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="25114-143">Следует объявить переменную объекта `Private`, чтобы защитить данные, принадлежащие текущему экземпляру, или переменную объекта `Private Shared`, чтобы защитить данные, общие для всех экземпляров.</span><span class="sxs-lookup"><span data-stu-id="25114-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="25114-144">Не следует использовать ключевое слово `Me` для предоставления объекта блокировки для данных экземпляра.</span><span class="sxs-lookup"><span data-stu-id="25114-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="25114-145">Если код, внешний для класса, имеет ссылку на экземпляр класса, он может использовать эту ссылку в качестве объекта блокировки для `SyncLock` блока, совершенно отличного от вашего, защищая различные данные.</span><span class="sxs-lookup"><span data-stu-id="25114-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="25114-146">Таким образом, класс и другой класс могут заблокировать друг друга от запуска несвязанных блоков `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="25114-147">Подобная блокировка строки может быть проблематичной, так как любой другой код в процессе, использующий одну и ту же строку, будет совместно использовать одну и ту же блокировку.</span><span class="sxs-lookup"><span data-stu-id="25114-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="25114-148">Не следует также использовать метод `Me.GetType` для предоставления объекта блокировки для общих данных.</span><span class="sxs-lookup"><span data-stu-id="25114-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="25114-149">Это происходит потому, что `GetType` всегда возвращает один и тот же `Type` объект для заданного имени класса.</span><span class="sxs-lookup"><span data-stu-id="25114-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="25114-150">Внешний код может вызвать `GetType` для класса и получить тот же объект блокировки, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="25114-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="25114-151">Это приведет к тому, что два класса блокируют друг друга из блоков `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="25114-152">Примеры</span><span class="sxs-lookup"><span data-stu-id="25114-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="25114-153">Описание</span><span class="sxs-lookup"><span data-stu-id="25114-153">Description</span></span>  
 <span data-ttu-id="25114-154">В следующем примере показан класс, который поддерживает простой список сообщений.</span><span class="sxs-lookup"><span data-stu-id="25114-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="25114-155">Он хранит сообщения в массиве и последнем используемом элементе этого массива в переменной.</span><span class="sxs-lookup"><span data-stu-id="25114-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="25114-156">`addAnotherMessage` процедура увеличивает последний элемент и сохраняет новое сообщение.</span><span class="sxs-lookup"><span data-stu-id="25114-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="25114-157">Эти две операции защищаются инструкциями `SyncLock` и `End SyncLock`, так как после увеличения последнего элемента новое сообщение должно быть сохранено до того, как любой другой поток снова сможет снова увеличить последний элемент.</span><span class="sxs-lookup"><span data-stu-id="25114-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="25114-158">Если класс `simpleMessageList` предоставил общий список сообщений между всеми экземплярами, переменные `messagesList` и `messagesLast` будут объявлены как `Shared`.</span><span class="sxs-lookup"><span data-stu-id="25114-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="25114-159">В этом случае переменную `messagesLock` также следует `Shared`, чтобы в каждом экземпляре использовался один объект блокировки.</span><span class="sxs-lookup"><span data-stu-id="25114-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="25114-160">Код</span><span class="sxs-lookup"><span data-stu-id="25114-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="25114-161">Описание</span><span class="sxs-lookup"><span data-stu-id="25114-161">Description</span></span>  
 <span data-ttu-id="25114-162">В следующем примере используются потоки и `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="25114-163">Пока используется оператор `SyncLock`, блок операторов является критическим разделом и `balance` никогда не становится отрицательным числом.</span><span class="sxs-lookup"><span data-stu-id="25114-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="25114-164">Можно закомментировать операторы `SyncLock` и `End SyncLock`, чтобы увидеть результат выхода из ключевого слова `SyncLock`.</span><span class="sxs-lookup"><span data-stu-id="25114-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="25114-165">Код</span><span class="sxs-lookup"><span data-stu-id="25114-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="25114-166">Комментарии</span><span class="sxs-lookup"><span data-stu-id="25114-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25114-167">См. также</span><span class="sxs-lookup"><span data-stu-id="25114-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="25114-168">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="25114-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
