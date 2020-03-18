---
title: Барьер
ms.date: 09/14/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
ms.openlocfilehash: 5aa34f7f39f4b9b626bea29372cf984f3cefb361
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138149"
---
# <a name="barrier"></a>Барьер

<xref:System.Threading.Barrier?displayProperty=nameWithType> — это определяемый пользователем примитив синхронизации, позволяющий нескольким потокам (которые называются *участниками*) параллельно осуществлять поэтапную работу с алгоритмом. Каждый участник выполняется до достижения точки барьера в коде. Барьер означает окончание одного этапа работы. Когда участник достигает барьера, он блокируется до тех пор, пока все участники не достигнут этого барьера. Когда все участники достигли барьера, можно при необходимости можно вызвать действие следующего этапа. Это действие следующего этапа может использоваться для выполнения действий одним потоком, пока все остальные потоки все еще остаются блокированными. После выполнения действия все участники разблокируются.  
  
 Во фрагменте кода ниже показан базовый шаблон барьера.  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 Полный пример можно найти в руководстве по [синхронизации параллельных операций с барьером](how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="adding-and-removing-participants"></a>Добавление и удаление участников

 При создании экземпляра <xref:System.Threading.Barrier> укажите количество участников. Вы можете также динамически добавлять или удалять участников в любое время. Например, если один участник решил свою часть задачи, можно сохранить результат, остановить выполнение этого потока и вызвать <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType>, чтобы уменьшить число участников барьера. При добавлении участника путем вызова <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType> возвращаемое значение определяет номер текущего этапа, что может быть полезно для инициализации действий нового участника.  
  
## <a name="broken-barriers"></a>Неисправные барьеры

 Если один из участников не достигает барьера, это может привести к возникновению взаимоблокировок. Во избежание взаимных блокировок используйте перегрузки метода <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType>, чтобы задать время ожидания и токен отмены. Эти перегрузки возвращают логическое значение, которое может проверить каждый участник перед переходом к следующему этапу.  
  
## <a name="post-phase-exceptions"></a>Исключения следующих этапов

 Если делегат следующего этапа создает исключение, оно инкапсулируется в объект <xref:System.Threading.BarrierPostPhaseException>, который затем передается всем участникам.  
  
## <a name="barrier-versus-continuewhenall"></a>Сравнение барьера и ContinueWhenAll

 Барьеры особенно полезны, когда потоки выполняют несколько этапов циклически. Если код требует выполнения только в один–два этапа, рассмотрите возможность использования объектов <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> с любым видом неявного объединения, в том числе:  
  
- <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>  
  
 Подробнее см. в разделе [Создание цепочки задач с помощью задач продолжения](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>См. также раздел

- [Объекты и функциональные возможности работы с потоками](threading-objects-and-features.md)
- [Практическое руководство. Синхронизация параллельных операций с барьером](how-to-synchronize-concurrent-operations-with-a-barrier.md)
