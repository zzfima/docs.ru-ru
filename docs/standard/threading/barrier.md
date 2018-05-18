---
title: Барьер (.NET Framework)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864571262d1c9c060235840424542856187341df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="barrier-net-framework"></a>Барьер (.NET Framework)
*Барьер* — это определяемый пользователем примитив синхронизации, позволяющий нескольким потокам (которые называются *участниками*) параллельно осуществлять поэтапную работу с алгоритмом. Каждый участник выполняется до достижения точки барьера в коде. Барьер означает окончание одного этапа работы. Когда участник достигает барьера, он блокируется до тех пор, пока все участники не достигнут этого барьера. Когда все участники достигли барьера, можно при необходимости можно вызвать действие следующего этапа. Это действие следующего этапа может использоваться для выполнения действий одним потоком, пока все остальные потоки все еще остаются блокированными. После выполнения действия все участники разблокируются.  
  
 Во фрагменте кода ниже показан базовый шаблон барьера.  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 Дополнительные сведения см. в руководстве по [синхронизации параллельных операций с барьером](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="adding-and-removing-participants"></a>Добавление и удаление участников  
 При создании <xref:System.Threading.Barrier> укажите число участников. Вы можете также динамически добавлять или удалять участников в любое время. Например, если один участник решил свою часть задачи, можно сохранить результат, остановить выполнение этого потока и вызвать <xref:System.Threading.Barrier.RemoveParticipant%2A>, чтобы уменьшить число участников барьера. При добавлении участника путем вызова <xref:System.Threading.Barrier.AddParticipant%2A> возвращаемое значение определяет номер текущего этапа, что может быть полезно для инициализации действий нового участника.  
  
## <a name="broken-barriers"></a>Неисправные барьеры  
 Если один из участников не достигает барьера, это может привести к возникновению взаимоблокировок. Во избежание взаимных блокировок используйте перегрузки метода <xref:System.Threading.Barrier.SignalAndWait%2A>, чтобы задать время ожидания и токен отмены. Эти перегрузки возвращают логическое значение, которое может проверить каждый участник перед переходом к следующему этапу.  
  
## <a name="post-phase-exceptions"></a>Исключения следующих этапов  
 Если делегат следующего этапа создает исключение, оно инкапсулируется в объект <xref:System.Threading.BarrierPostPhaseException>, который затем передается всем участникам.  
  
## <a name="barrier-versus-continuewhenall"></a>Сравнение барьера и ContinueWhenAll  
 Барьеры особенно полезны, когда потоки выполняют несколько этапов циклически. Если код требует выполнения только в один–два этапа, рассмотрите возможность использования объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> с любым видом неявного объединения, в том числе:  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 Подробнее см. в разделе [Создание цепочки задач с помощью задач продолжения](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>См. также  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Практическое руководство. Синхронизация параллельных операций с барьером](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)
