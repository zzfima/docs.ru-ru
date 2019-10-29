---
title: Оптимистическая блокировка
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
ms.openlocfilehash: ddb53c9224d56803c3528d79c5ccdf5534b9ab03
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039815"
---
# <a name="optimistic-concurrency"></a><span data-ttu-id="770ca-102">Оптимистическая блокировка</span><span class="sxs-lookup"><span data-stu-id="770ca-102">Optimistic Concurrency</span></span>
<span data-ttu-id="770ca-103">В многопользовательской среде предусмотрены две модели обновления данных в базе данных: оптимистичный параллелизм и пессимистичный параллелизм.</span><span class="sxs-lookup"><span data-stu-id="770ca-103">In a multiuser environment, there are two models for updating data in a database: optimistic concurrency and pessimistic concurrency.</span></span> <span data-ttu-id="770ca-104">Объект <xref:System.Data.DataSet> предназначен для стимулирования использования оптимистичного параллелизма для длительный действий, таких как удаленный доступ к данным и взаимодействие с данными.</span><span class="sxs-lookup"><span data-stu-id="770ca-104">The <xref:System.Data.DataSet> object is designed to encourage the use of optimistic concurrency for long-running activities, such as remoting data and interacting with data.</span></span>  
  
 <span data-ttu-id="770ca-105">Пессимистичный параллелизм предусматривает блокировку строк в источнике данных, что позволяет запретить другим пользователям модификацию данных, которая может отрицательно повлиять на работу текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="770ca-105">Pessimistic concurrency involves locking rows at the data source to prevent other users from modifying data in a way that affects the current user.</span></span> <span data-ttu-id="770ca-106">В пессимистической модели, когда пользователь выполняет действие, вызывающее применение блокировки, другие пользователи не могут выполнять действия, которые могли бы конфликтовать с этой блокировкой, до тех пор как владелец блокировки ее не снимет.</span><span class="sxs-lookup"><span data-stu-id="770ca-106">In a pessimistic model, when a user performs an action that causes a lock to be applied, other users cannot perform actions that would conflict with the lock until the lock owner releases it.</span></span> <span data-ttu-id="770ca-107">Эта модель в основном используется в таких средах, где наблюдается интенсивная конкуренция по доступу к данным, поэтому расходы на защиту данных с помощью блокировок оказываются меньше по сравнению с расходами на откаты транзакций, обусловленные возникновением конфликтов параллельного доступа.</span><span class="sxs-lookup"><span data-stu-id="770ca-107">This model is primarily used in environments where there is heavy contention for data, so that the cost of protecting data with locks is less than the cost of rolling back transactions if concurrency conflicts occur.</span></span>  
  
 <span data-ttu-id="770ca-108">Поэтому в модели с пессимистичным параллелизмом пользователь, обновляющий строку, устанавливает блокировку.</span><span class="sxs-lookup"><span data-stu-id="770ca-108">Therefore, in a pessimistic concurrency model, a user who updates a row establishes a lock.</span></span> <span data-ttu-id="770ca-109">До тех пор пока пользователь не закончит обновление и не снимет блокировку, больше никто другой не сможет вносить изменения в эту строку.</span><span class="sxs-lookup"><span data-stu-id="770ca-109">Until the user has finished the update and released the lock, no one else can change that row.</span></span> <span data-ttu-id="770ca-110">Это означает, что пессимистичный параллелизм является наиболее подходящим в тех ситуациях, когда блокировки устанавливаются на короткое время, например как при программной обработке записей.</span><span class="sxs-lookup"><span data-stu-id="770ca-110">For this reason, pessimistic concurrency is best implemented when lock times will be short, as in programmatic processing of records.</span></span> <span data-ttu-id="770ca-111">Применение пессимистичного параллелизма становится препятствием для масштабирования приложения, когда пользователи взаимодействуют с данными и вызывают блокировку записей на относительно большие промежутки времени.</span><span class="sxs-lookup"><span data-stu-id="770ca-111">Pessimistic concurrency is not a scalable option when users are interacting with data and causing records to be locked for relatively large periods of time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="770ca-112">Если в приложении требуется обновлять несколько строк в одной операции, то создание транзакций обеспечивает лучшее масштабирование по сравнению с использованием пессимистичных блокировок.</span><span class="sxs-lookup"><span data-stu-id="770ca-112">If you need to update multiple rows in the same operation, then creating a transaction is a more scalable option than using pessimistic locking.</span></span>  
  
 <span data-ttu-id="770ca-113">В отличие от этого, пользователи, применяющие оптимистичный параллелизм, не блокируют строку при ее чтении.</span><span class="sxs-lookup"><span data-stu-id="770ca-113">By contrast, users who use optimistic concurrency do not lock a row when reading it.</span></span> <span data-ttu-id="770ca-114">Когда пользователю требуется обновить строку, приложение должно определить, не изменялась ли эта строка другим пользователем после того, как она была открыта для чтения.</span><span class="sxs-lookup"><span data-stu-id="770ca-114">When a user wants to update a row, the application must determine whether another user has changed the row since it was read.</span></span> <span data-ttu-id="770ca-115">Оптимистичный параллелизм обычно используется в средах, характеризующихся низкой конкуренцией за данные.</span><span class="sxs-lookup"><span data-stu-id="770ca-115">Optimistic concurrency is generally used in environments with a low contention for data.</span></span> <span data-ttu-id="770ca-116">Применение оптимистичного параллелизма способствует повышению производительности благодаря тому, что не требуется блокировка записей, которая требует дополнительных ресурсов сервера.</span><span class="sxs-lookup"><span data-stu-id="770ca-116">Optimistic concurrency improves performance because no locking of records is required, and locking of records requires additional server resources.</span></span> <span data-ttu-id="770ca-117">Кроме того, для блокировки записей требуется постоянное соединение с сервером базы данных.</span><span class="sxs-lookup"><span data-stu-id="770ca-117">Also, in order to maintain record locks, a persistent connection to the database server is required.</span></span> <span data-ttu-id="770ca-118">При использовании модели оптимистичного параллелизма такая необходимость отсутствует, поэтому соединения с сервером можно применять для обслуживания большего количества клиентов за меньшее время.</span><span class="sxs-lookup"><span data-stu-id="770ca-118">Because this is not the case in an optimistic concurrency model, connections to the server are free to serve a larger number of clients in less time.</span></span>  
  
 <span data-ttu-id="770ca-119">В модели оптимистичного параллелизма конфликтом параллельного доступа считается ситуация, когда вслед за получением пользователем значения из базы данных другой пользователь изменяет это значение до того, как первый пользователь попытается его изменить.</span><span class="sxs-lookup"><span data-stu-id="770ca-119">In an optimistic concurrency model, a violation is considered to have occurred if, after a user receives a value from the database, another user modifies the value before the first user has attempted to modify it.</span></span> <span data-ttu-id="770ca-120">Разрешение конфликта параллельного доступа лучше всего показать, рассмотрев следующий пример.</span><span class="sxs-lookup"><span data-stu-id="770ca-120">How the server resolves a concurrency violation is best shown by first describing the following example.</span></span>  
  
 <span data-ttu-id="770ca-121">В следующих таблицах рассматривается пример оптимистичного параллелизма.</span><span class="sxs-lookup"><span data-stu-id="770ca-121">The following tables follow an example of optimistic concurrency.</span></span>  
  
 <span data-ttu-id="770ca-122">В 13:00 Пользователь1 считывает из базы данных строку со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="770ca-122">At 1:00 p.m., User1 reads a row from the database with the following values:</span></span>  
  
 <span data-ttu-id="770ca-123">**CustID LastName FirstName**</span><span class="sxs-lookup"><span data-stu-id="770ca-123">**CustID     LastName     FirstName**</span></span>  
  
 <span data-ttu-id="770ca-124">101          Smith             Bob</span><span class="sxs-lookup"><span data-stu-id="770ca-124">101          Smith             Bob</span></span>  
  
|<span data-ttu-id="770ca-125">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="770ca-125">Column name</span></span>|<span data-ttu-id="770ca-126">Исходное значение</span><span class="sxs-lookup"><span data-stu-id="770ca-126">Original value</span></span>|<span data-ttu-id="770ca-127">Текущее значение</span><span class="sxs-lookup"><span data-stu-id="770ca-127">Current value</span></span>|<span data-ttu-id="770ca-128">Значение в базе данных</span><span class="sxs-lookup"><span data-stu-id="770ca-128">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="770ca-129">CustID</span><span class="sxs-lookup"><span data-stu-id="770ca-129">CustID</span></span>|<span data-ttu-id="770ca-130">101</span><span class="sxs-lookup"><span data-stu-id="770ca-130">101</span></span>|<span data-ttu-id="770ca-131">101</span><span class="sxs-lookup"><span data-stu-id="770ca-131">101</span></span>|<span data-ttu-id="770ca-132">101</span><span class="sxs-lookup"><span data-stu-id="770ca-132">101</span></span>|  
|<span data-ttu-id="770ca-133">LastName</span><span class="sxs-lookup"><span data-stu-id="770ca-133">LastName</span></span>|<span data-ttu-id="770ca-134">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-134">Smith</span></span>|<span data-ttu-id="770ca-135">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-135">Smith</span></span>|<span data-ttu-id="770ca-136">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-136">Smith</span></span>|  
|<span data-ttu-id="770ca-137">FirstName</span><span class="sxs-lookup"><span data-stu-id="770ca-137">FirstName</span></span>|<span data-ttu-id="770ca-138">Bob</span><span class="sxs-lookup"><span data-stu-id="770ca-138">Bob</span></span>|<span data-ttu-id="770ca-139">Bob</span><span class="sxs-lookup"><span data-stu-id="770ca-139">Bob</span></span>|<span data-ttu-id="770ca-140">Bob</span><span class="sxs-lookup"><span data-stu-id="770ca-140">Bob</span></span>|  
  
 <span data-ttu-id="770ca-141">В 13:01 Пользователь2 считывает ту же строку.</span><span class="sxs-lookup"><span data-stu-id="770ca-141">At 1:01 p.m., User2 reads the same row.</span></span>  
  
 <span data-ttu-id="770ca-142">В 1:03 г. Пользователь2 изменяет **имя** с "Bob" на "Роберт" и обновляет базу данных.</span><span class="sxs-lookup"><span data-stu-id="770ca-142">At 1:03 p.m., User2 changes **FirstName** from "Bob" to "Robert" and updates the database.</span></span>  
  
|<span data-ttu-id="770ca-143">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="770ca-143">Column name</span></span>|<span data-ttu-id="770ca-144">Исходное значение</span><span class="sxs-lookup"><span data-stu-id="770ca-144">Original value</span></span>|<span data-ttu-id="770ca-145">Текущее значение</span><span class="sxs-lookup"><span data-stu-id="770ca-145">Current value</span></span>|<span data-ttu-id="770ca-146">Значение в базе данных</span><span class="sxs-lookup"><span data-stu-id="770ca-146">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="770ca-147">CustID</span><span class="sxs-lookup"><span data-stu-id="770ca-147">CustID</span></span>|<span data-ttu-id="770ca-148">101</span><span class="sxs-lookup"><span data-stu-id="770ca-148">101</span></span>|<span data-ttu-id="770ca-149">101</span><span class="sxs-lookup"><span data-stu-id="770ca-149">101</span></span>|<span data-ttu-id="770ca-150">101</span><span class="sxs-lookup"><span data-stu-id="770ca-150">101</span></span>|  
|<span data-ttu-id="770ca-151">LastName</span><span class="sxs-lookup"><span data-stu-id="770ca-151">LastName</span></span>|<span data-ttu-id="770ca-152">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-152">Smith</span></span>|<span data-ttu-id="770ca-153">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-153">Smith</span></span>|<span data-ttu-id="770ca-154">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-154">Smith</span></span>|  
|<span data-ttu-id="770ca-155">FirstName</span><span class="sxs-lookup"><span data-stu-id="770ca-155">FirstName</span></span>|<span data-ttu-id="770ca-156">Bob</span><span class="sxs-lookup"><span data-stu-id="770ca-156">Bob</span></span>|<span data-ttu-id="770ca-157">Robert</span><span class="sxs-lookup"><span data-stu-id="770ca-157">Robert</span></span>|<span data-ttu-id="770ca-158">Bob</span><span class="sxs-lookup"><span data-stu-id="770ca-158">Bob</span></span>|  
  
 <span data-ttu-id="770ca-159">Эта операция обновления завершается успешно, поскольку значения в базе данных ко времени обновления соответствуют первоначальным значениям, которые имеются в распоряжении Пользователя2.</span><span class="sxs-lookup"><span data-stu-id="770ca-159">The update succeeds because the values in the database at the time of update match the original values that User2 has.</span></span>  
  
 <span data-ttu-id="770ca-160">В 13:05 Пользователь1 изменяет значение FirstName с «Bob» на «James» и пытается обновить строку.</span><span class="sxs-lookup"><span data-stu-id="770ca-160">At 1:05 p.m., User1 changes "Bob"'s first name to "James" and tries to update the row.</span></span>  
  
|<span data-ttu-id="770ca-161">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="770ca-161">Column name</span></span>|<span data-ttu-id="770ca-162">Исходное значение</span><span class="sxs-lookup"><span data-stu-id="770ca-162">Original value</span></span>|<span data-ttu-id="770ca-163">Текущее значение</span><span class="sxs-lookup"><span data-stu-id="770ca-163">Current value</span></span>|<span data-ttu-id="770ca-164">Значение в базе данных</span><span class="sxs-lookup"><span data-stu-id="770ca-164">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="770ca-165">CustID</span><span class="sxs-lookup"><span data-stu-id="770ca-165">CustID</span></span>|<span data-ttu-id="770ca-166">101</span><span class="sxs-lookup"><span data-stu-id="770ca-166">101</span></span>|<span data-ttu-id="770ca-167">101</span><span class="sxs-lookup"><span data-stu-id="770ca-167">101</span></span>|<span data-ttu-id="770ca-168">101</span><span class="sxs-lookup"><span data-stu-id="770ca-168">101</span></span>|  
|<span data-ttu-id="770ca-169">LastName</span><span class="sxs-lookup"><span data-stu-id="770ca-169">LastName</span></span>|<span data-ttu-id="770ca-170">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-170">Smith</span></span>|<span data-ttu-id="770ca-171">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-171">Smith</span></span>|<span data-ttu-id="770ca-172">Smith</span><span class="sxs-lookup"><span data-stu-id="770ca-172">Smith</span></span>|  
|<span data-ttu-id="770ca-173">FirstName</span><span class="sxs-lookup"><span data-stu-id="770ca-173">FirstName</span></span>|<span data-ttu-id="770ca-174">Bob</span><span class="sxs-lookup"><span data-stu-id="770ca-174">Bob</span></span>|<span data-ttu-id="770ca-175">James</span><span class="sxs-lookup"><span data-stu-id="770ca-175">James</span></span>|<span data-ttu-id="770ca-176">Robert</span><span class="sxs-lookup"><span data-stu-id="770ca-176">Robert</span></span>|  
  
 <span data-ttu-id="770ca-177">В этот момент Пользователь1 обнаруживает нарушение оптимистичного параллелизма, поскольку значение в базе данных («Robert») больше не соответствует первоначальному значению, которое ожидал найти Пользователь1 («Bob»).</span><span class="sxs-lookup"><span data-stu-id="770ca-177">At this point, User1 encounters an optimistic concurrency violation because the value in the database ("Robert") no longer matches the original value that User1 was expecting ("Bob").</span></span> <span data-ttu-id="770ca-178">Это нарушение параллелизма просто позволяет узнать о том, что обновление окончилось неудачей.</span><span class="sxs-lookup"><span data-stu-id="770ca-178">The concurrency violation simply lets you know that the update failed.</span></span> <span data-ttu-id="770ca-179">После этого нужно принять решение, следует ли перезаписать изменения, внесенные Пользователем2, изменениями, которые внес Пользователь1, или отменить изменения Пользователя1.</span><span class="sxs-lookup"><span data-stu-id="770ca-179">The decision now needs to be made whether to overwrite the changes supplied by User2 with the changes supplied by User1, or to cancel the changes by User1.</span></span>  
  
## <a name="testing-for-optimistic-concurrency-violations"></a><span data-ttu-id="770ca-180">Проверка на наличие нарушений оптимистичного параллелизма</span><span class="sxs-lookup"><span data-stu-id="770ca-180">Testing for Optimistic Concurrency Violations</span></span>  
 <span data-ttu-id="770ca-181">Существует несколько методов проверки на наличие нарушений оптимистичного параллелизма.</span><span class="sxs-lookup"><span data-stu-id="770ca-181">There are several techniques for testing for an optimistic concurrency violation.</span></span> <span data-ttu-id="770ca-182">Один из этих методов предусматривает включение столбца метки времени в таблицу.</span><span class="sxs-lookup"><span data-stu-id="770ca-182">One involves including a timestamp column in the table.</span></span> <span data-ttu-id="770ca-183">Базы данных обычно предоставляют возможность использования отметок времени, которые могут служить для определения даты и времени последнего обновления записи.</span><span class="sxs-lookup"><span data-stu-id="770ca-183">Databases commonly provide timestamp functionality that can be used to identify the date and time when the record was last updated.</span></span> <span data-ttu-id="770ca-184">При использовании этого метода в определение таблицы включается столбец метки времени.</span><span class="sxs-lookup"><span data-stu-id="770ca-184">Using this technique, a timestamp column is included in the table definition.</span></span> <span data-ttu-id="770ca-185">После каждого обновления записи обновляется также метка времени, отражая текущую дату и время.</span><span class="sxs-lookup"><span data-stu-id="770ca-185">Whenever the record is updated, the timestamp is updated to reflect the current date and time.</span></span> <span data-ttu-id="770ca-186">При проверке на наличие нарушений оптимистичного параллелизма при любом запросе к содержимому таблицы происходит возврат значений столбца метки времени.</span><span class="sxs-lookup"><span data-stu-id="770ca-186">In a test for optimistic concurrency violations, the timestamp column is returned with any query of the contents of the table.</span></span> <span data-ttu-id="770ca-187">При попытке обновления это значение метки времени из базы данных сравнивается с первоначальным значением метки времени, содержащимся в измененной строке.</span><span class="sxs-lookup"><span data-stu-id="770ca-187">When an update is attempted, the timestamp value in the database is compared to the original timestamp value contained in the modified row.</span></span> <span data-ttu-id="770ca-188">Если эти значения совпадают, операция обновления выполняется и столбец метки времени обновляется с указанием текущего времени, чтобы отразить факт обновления.</span><span class="sxs-lookup"><span data-stu-id="770ca-188">If they match, the update is performed and the timestamp column is updated with the current time to reflect the update.</span></span> <span data-ttu-id="770ca-189">Если эти значения не совпадают, то возникает конфликт оптимистичного параллелизма.</span><span class="sxs-lookup"><span data-stu-id="770ca-189">If they do not match, an optimistic concurrency violation has occurred.</span></span>  
  
 <span data-ttu-id="770ca-190">Еще один метод проверки на наличие нарушения оптимистичного параллелизма состоит в проверке того, что все первоначальные значения полей в строке все еще соответствуют находящимся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="770ca-190">Another technique for testing for an optimistic concurrency violation is to verify that all the original column values in a row still match those found in the database.</span></span> <span data-ttu-id="770ca-191">Например, рассмотрим следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="770ca-191">For example, consider the following query:</span></span>  
  
```sql
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 <span data-ttu-id="770ca-192">Чтобы проверить наличие нарушения оптимистической блокировки при обновлении строки в **Table1**, выполните следующую инструкцию UPDATE:</span><span class="sxs-lookup"><span data-stu-id="770ca-192">To test for an optimistic concurrency violation when updating a row in **Table1**, you would issue the following UPDATE statement:</span></span>  
  
```sql
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 <span data-ttu-id="770ca-193">При условии, что первоначальные значения равны значениям в базе данных, обновление выполняется.</span><span class="sxs-lookup"><span data-stu-id="770ca-193">As long as the original values match the values in the database, the update is performed.</span></span> <span data-ttu-id="770ca-194">Если же какое-то значение было изменено, то при обновлении изменение строки не происходит, поскольку в предложении WHERE не обнаруживается совпадение.</span><span class="sxs-lookup"><span data-stu-id="770ca-194">If a value has been modified, the update will not modify the row because the WHERE clause will not find a match.</span></span>  
  
 <span data-ttu-id="770ca-195">Обратите внимание, что всегда рекомендуется возвращать уникальное значение первичного ключа в каждом конкретном запросе.</span><span class="sxs-lookup"><span data-stu-id="770ca-195">Note that it is recommended to always return a unique primary key value in your query.</span></span> <span data-ttu-id="770ca-196">В противном случае в предыдущей инструкции UPDATE может произойти обновление нескольких строк, что может не соответствовать намерениям.</span><span class="sxs-lookup"><span data-stu-id="770ca-196">Otherwise, the preceding UPDATE statement may update more than one row, which might not be your intent.</span></span>  
  
 <span data-ttu-id="770ca-197">Если столбец в источнике данных допускает значения NULL, то может потребоваться дополнить предложение WHERE для проверки на наличие согласующихся ссылок NULL в локальной таблице и в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="770ca-197">If a column at your data source allows nulls, you may need to extend your WHERE clause to check for a matching null reference in your local table and at the data source.</span></span> <span data-ttu-id="770ca-198">Например, в следующей инструкции UPDATE проверяется, что ссылка NULL в локальной строке все еще соответствует ссылке NULL в источнике данных или что значение в локальной строке все еще соответствует значению в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="770ca-198">For example, the following UPDATE statement verifies that a null reference in the local row still matches a null reference at the data source, or that the value in the local row still matches the value at the data source.</span></span>  
  
```sql
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 <span data-ttu-id="770ca-199">При использовании модели оптимистичного параллелизма можно также выбрать менее строгие критерии.</span><span class="sxs-lookup"><span data-stu-id="770ca-199">You may also choose to apply less restrictive criteria when using an optimistic concurrency model.</span></span> <span data-ttu-id="770ca-200">Например, если в предложении WHERE используются только столбцы первичного ключа, то перезапись данных происходит независимо от того, произошло ли обновление других столбцов со времени выполнения последнего запроса.</span><span class="sxs-lookup"><span data-stu-id="770ca-200">For example, using only the primary key columns in the WHERE clause causes the data to be overwritten regardless of whether the other columns have been updated since the last query.</span></span> <span data-ttu-id="770ca-201">Предложение WHERE также можно применять только к конкретным столбцам, в результате чего перезапись данных будет выполняться, только если со времени последнего запроса к определенным полям они не обновлялись.</span><span class="sxs-lookup"><span data-stu-id="770ca-201">You can also apply a WHERE clause only to specific columns, resulting in data being overwritten unless particular fields have been updated since they were last queried.</span></span>  
  
### <a name="the-dataadapterrowupdated-event"></a><span data-ttu-id="770ca-202">Событие DataAdapter.RowUpdated</span><span class="sxs-lookup"><span data-stu-id="770ca-202">The DataAdapter.RowUpdated Event</span></span>  
 <span data-ttu-id="770ca-203">Событие **RowUpdated** объекта <xref:System.Data.Common.DataAdapter> можно использовать в сочетании с методами, описанными выше, чтобы обеспечить уведомление для приложения о нарушениях оптимистической блокировки.</span><span class="sxs-lookup"><span data-stu-id="770ca-203">The **RowUpdated** event of the <xref:System.Data.Common.DataAdapter> object can be used in conjunction with the techniques described earlier, to provide notification to your application of optimistic concurrency violations.</span></span> <span data-ttu-id="770ca-204">**RowUpdated** происходит после каждой попытки обновить **измененную** строку из **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="770ca-204">**RowUpdated** occurs after each attempt to update a **Modified** row from a **DataSet**.</span></span> <span data-ttu-id="770ca-205">Это позволяет включать в приложение специальный код обработки, в том числе обеспечивающий обработку при возникновении исключений, добавление пользовательских сведений об ошибке, введение программных средств повторного выполнения и т. д.</span><span class="sxs-lookup"><span data-stu-id="770ca-205">This enables you to add special handling code, including processing when an exception occurs, adding custom error information, adding retry logic, and so on.</span></span> <span data-ttu-id="770ca-206">Объект <xref:System.Data.Common.RowUpdatedEventArgs> возвращает свойство **рекордсаффектед** , содержащее количество строк, затронутых определенной командой Update для измененной строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="770ca-206">The <xref:System.Data.Common.RowUpdatedEventArgs> object returns a **RecordsAffected** property containing the number of rows affected by a particular update command for a modified row in a table.</span></span> <span data-ttu-id="770ca-207">Настроив команду Update для проверки оптимистического параллелизма, свойство **рекордсаффектед** в результате возвращает значение 0 при возникновении нарушения оптимистического параллелизма, поскольку записи не обновлялись.</span><span class="sxs-lookup"><span data-stu-id="770ca-207">By setting the update command to test for optimistic concurrency, the **RecordsAffected** property will, as a result, return a value of 0 when an optimistic concurrency violation has occurred, because no records were updated.</span></span> <span data-ttu-id="770ca-208">В таком случае вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="770ca-208">If this is the case, an exception is thrown.</span></span> <span data-ttu-id="770ca-209">Событие **RowUpdated** позволяет справиться с этим экземпляром и избежать исключения, установив соответствующее значение **ровупдатедевентаргс. status** , например **UpdateStatus. скипкуррентров**.</span><span class="sxs-lookup"><span data-stu-id="770ca-209">The **RowUpdated** event enables you to handle this occurrence and avoid the exception by setting an appropriate **RowUpdatedEventArgs.Status** value, such as **UpdateStatus.SkipCurrentRow**.</span></span> <span data-ttu-id="770ca-210">Дополнительные сведения о событии **RowUpdated** см. в разделе [Обработка событий DataAdapter](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="770ca-210">For more information about the **RowUpdated** event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
 <span data-ttu-id="770ca-211">При необходимости можно установить **DataAdapter. континуеупдатеонеррор** в **значение true**, перед вызовом **Update**и ответ на сведения об ошибке, хранящиеся в свойстве **роверрор** определенной строки после завершения **обновления** .</span><span class="sxs-lookup"><span data-stu-id="770ca-211">Optionally, you can set **DataAdapter.ContinueUpdateOnError** to **true**, before calling **Update**, and respond to the error information stored in the **RowError** property of a particular row when the **Update** is completed.</span></span> <span data-ttu-id="770ca-212">Дополнительные сведения см. в разделе [сведения об ошибках строки](./dataset-datatable-dataview/row-error-information.md).</span><span class="sxs-lookup"><span data-stu-id="770ca-212">For more information, see [Row Error Information](./dataset-datatable-dataview/row-error-information.md).</span></span>  
  
## <a name="optimistic-concurrency-example"></a><span data-ttu-id="770ca-213">Пример оптимистического управления параллелизмом</span><span class="sxs-lookup"><span data-stu-id="770ca-213">Optimistic Concurrency Example</span></span>  
 <span data-ttu-id="770ca-214">Ниже приведен простой пример, который задает **UpdateCommand** объекта **DataAdapter** для проверки на оптимистичный параллелизм, а затем использует событие **RowUpdated** для проверки на наличие нарушений оптимистической блокировки.</span><span class="sxs-lookup"><span data-stu-id="770ca-214">The following is a simple example that sets the **UpdateCommand** of a **DataAdapter** to test for optimistic concurrency, and then uses the **RowUpdated** event to test for optimistic concurrency violations.</span></span> <span data-ttu-id="770ca-215">При обнаружении нарушения оптимистичного параллелизма приложение устанавливает **роверрор** строки, для которой было выдано обновление, чтобы отразить нарушение оптимистического параллелизма.</span><span class="sxs-lookup"><span data-stu-id="770ca-215">When an optimistic concurrency violation is encountered, the application sets the **RowError** of the row that the update was issued for to reflect an optimistic concurrency violation.</span></span>  
  
 <span data-ttu-id="770ca-216">Обратите внимание, что значения параметров, передаваемые в предложение WHERE команды UPDATE, сопоставляются **исходным** значениям соответствующих столбцов.</span><span class="sxs-lookup"><span data-stu-id="770ca-216">Note that the parameter values passed to the WHERE clause of the UPDATE command are mapped to the **Original** values of their respective columns.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then   
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName", connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)   
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="770ca-217">См. также</span><span class="sxs-lookup"><span data-stu-id="770ca-217">See also</span></span>

- [<span data-ttu-id="770ca-218">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="770ca-218">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="770ca-219">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="770ca-219">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="770ca-220">Сведения об ошибках строк</span><span class="sxs-lookup"><span data-stu-id="770ca-220">Row Error Information</span></span>](./dataset-datatable-dataview/row-error-information.md)
- [<span data-ttu-id="770ca-221">Транзакции и параллельность</span><span class="sxs-lookup"><span data-stu-id="770ca-221">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="770ca-222">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="770ca-222">ADO.NET Overview</span></span>](ado-net-overview.md)
