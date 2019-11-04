---
title: Уведомления о сборке мусора
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
ms.openlocfilehash: d5646c4969c95350ab4cd63b16f6f99ffba3a4ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131536"
---
# <a name="garbage-collection-notifications"></a>Уведомления о сборке мусора
В некоторых случаях полная сборка мусора (сборка объектов поколения 2) средой CLR может отрицательно сказаться на производительности. Это может стать проблемой, особенно для серверов, которые обрабатывают большие объемы запросов. Длительный процесс сборки может привести к потере запросов из-за превышения времени ожидания. Чтобы предотвратить запуск полной сборки мусора в критически важные периоды, вы можете настроить уведомления о ее приближении. Это позволит принять меры и перенести нагрузку на другой экземпляр сервера. Также вы можете самостоятельно запустить сборку мусора на экземплярах сервера, которые в текущий момент не применяются для обработки запросов.  
  
 Метод <xref:System.GC.RegisterForFullGCNotification%2A> позволяет зарегистрироваться для получения уведомлений о приближении полной сборки мусора. Вы получите два уведомления: при приближении полной сборки мусора и по ее завершении.  
  
> [!WARNING]
> Только блокировка сборки мусора создает уведомления. Если включен элемент конфигурации [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), при фоновой сборке мусора уведомления не создаются.  
  
 Чтобы определить, когда было создано уведомление, используйте методы <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A>. Как правило, они вызываются в цикле `while`, чтобы постоянно получать перечисление <xref:System.GCNotificationStatus> с информацией о состоянии уведомления. Если вы получите значение <xref:System.GCNotificationStatus.Succeeded>, можете выполнить следующие действия:  
  
- В ответ на уведомление, полученное с помощью метода <xref:System.GC.WaitForFullGCApproach%2A>, перераспределите рабочую нагрузку и при необходимости самостоятельно запустите сборку мусора.  
  
- В ответ на уведомление, полученное с помощью метода <xref:System.GC.WaitForFullGCComplete%2A>, восстановите доступность текущего экземпляра сервера для обработки запросов. Вы также можете собирать сведения. Например, метод <xref:System.GC.CollectionCount%2A> позволяет зафиксировать количество сборок мусора.  
  
 Методы <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A> следует использовать совместно. Вызов только одного из них может привести к непредсказуемым результатам.  
  
## <a name="full-garbage-collection"></a>Полная сборка мусора  
 Среда выполнения инициирует полную сборку мусора в одной из следующих ситуаций:  
  
- В состояние поколения 2 переведен достаточный объем памяти, чтобы выполнить очередную сборку мусора поколения 2.  
  
- В состояние кучи для массивных объектов переведен достаточный объем памяти, чтобы выполнить очередную сборку мусора поколения 2.  
  
- Уровень сборки мусора поколения 1 повышен до поколения 2 в силу других факторов.  
  
 Пороговые значения, указанные в методе <xref:System.GC.RegisterForFullGCNotification%2A>, применяются к двум первым ситуациям. Но в первом случае вы не обязательно будете получать уведомление в момент, который точно соответствует заданному пропорциональному значению пороговых уровней. Для этого есть две причины:  
  
- в среде выполнения не проверяется каждое выделение небольших объектов (чтобы не снижать производительность);  
  
- перевод памяти в состояние поколения 2 выполняется только при сборке мусора поколения 1.  
  
 В третьем сценарии также нельзя точно определить время получения уведомлений. Этот подход не дает гарантий, он очень полезен для устранения негативных последствий несвоевременной полной сборки мусора, так как позволяет перенаправить запросы на время сборки или вызвать ее самостоятельно в более удобное время.  
  
## <a name="notification-threshold-parameters"></a>Параметры порогов уведомлений  
 Метод <xref:System.GC.RegisterForFullGCNotification%2A> имеет два параметра, которые позволяют задать пороговые значения для объектов поколения 2 и кучи больших объектов. При достижении этих значений будет создаваться уведомление о сборке мусора. Эти параметры описаны в приведенной ниже таблице.  
  
|Параметр|ОПИСАНИЕ|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Число от 1 до 99, которое указывает условия для создания уведомления в зависимости от объектов, переведенных в состояние поколения 2.|  
|`largeObjectHeapThreshold`|Число от 1 до 99, которое указывает условия для создания уведомления в зависимости от объема объектов, помещенных в кучу больших объектов.|  
  
 Если вы укажете очень большое значение, вероятность получить уведомление повышается. Но вам придется довольно долго ждать, пока в среде выполнения будет вызвана сборка мусора. Если вы запустите сборку мусора самостоятельно, будет освобождено больше объектов, чем при сборке мусора, запущенной в среде выполнения.  
  
 Если вы укажете очень низкое значение, сборку мусора может запуститься в среде выполнения раньше, чем вы получите и (или) обработаете уведомление.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>ОПИСАНИЕ  
 В приведенном ниже примере группа серверов обрабатывает входящие веб-запросы. Для имитации рабочей нагрузки по обработке запросов в коллекцию <xref:System.Collections.Generic.List%601> добавляются массивы байтов. Каждый сервер регистрируется для получения уведомлений о сборке мусора и запускает поток с пользовательским методом `WaitForFullGCProc` для постоянного наблюдения за перечислением <xref:System.GCNotificationStatus>, которое возвращают методы <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A>.  
  
 Методы <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A> при получении уведомлений вызывают соответствующие пользовательские методы для обработки событий.  
  
- `OnFullGCApproachNotify`  
  
     Этот метод вызывает пользовательский метод `RedirectRequests`, который передает на сервер очереди команду прекратить отправку запросов на свой сервер. Для имитации этого поведения переменной `bAllocate` уровня класса присваивается значение `false`. После этого выделение новых объектов прекращается.  
  
     Теперь вызывается пользовательский метод `FinishExistingRequests`, чтобы завершить обработку текущих запросов на сервере. Для имитации этого действия коллекция <xref:System.Collections.Generic.List%601> очищается.  
  
     И, наконец, в период низкой нагрузки вызывается сборка мусора.  
  
- `OnFullGCCompleteNotify`  
  
     Этот метод вызывает пользовательский метод `AcceptRequests`, чтобы возобновить прием запросов, так как теперь серверу не угрожает полная сборка мусора. Для имитации этого поведения переменной `bAllocate` уровня класса присваивается значение `true`, чтобы новые объекты снова добавлялись в коллекцию <xref:System.Collections.Generic.List%601>.  
  
 Следующий код содержит метод `Main` для нашего примера:  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 Следующий код содержит пользовательский метод `WaitForFullGCProc`, при помощи которого выполняется непрерывный цикл проверки уведомлений о сборке мусора:  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 Следующий код содержит метод `OnFullGCApproachNotify`, вызываемый из  
  
 Метод `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 Следующий код содержит метод `OnFullGCApproachComplete`, вызываемый из  
  
 Метод `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 Приведенный ниже код содержит пользовательские методы, которые вызываются из методов `OnFullGCApproachNotify` и `OnFullGCCompleteNotify`. Пользовательские методы позволяют перенаправить запросы, завершить обработку существующих запросов и возобновить прием запросов после полной сборки мусора.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 Полный пример кода выглядит следующим образом:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Сборка мусора](../../../docs/standard/garbage-collection/index.md)
