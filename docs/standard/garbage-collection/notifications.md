---
title: "Уведомления о сборке мусора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a>Уведомления о сборке мусора
В некоторых случаях полная сборка мусора (сборка объектов поколения 2) средой CLR может отрицательно сказаться на производительности. Это может стать проблемой, особенно с серверами, которые обрабатывают большие объемы запросов; в этом случае длинное мусора может вызвать тайм-аут запроса. Чтобы предотвратить полной сборки мусора во время критического периода, чтобы настроить уведомления, приближается к полной сборкой мусора и принимать меры по перенаправлению нагрузки на другой экземпляр сервера. Вы можете также вызвать сборку мусора самостоятельно, при условии, что текущий экземпляр сервера не требуется обрабатывать запросы.  
  
 <xref:System.GC.RegisterForFullGCNotification%2A> Метод регистрирует для уведомления, когда среда выполнения получает информацию, достигает полной сборкой мусора. Это уведомление, состоит из двух частей: при приближении полной сборки мусора, и после завершения полной сборки мусора.  
  
> [!WARNING]
>  Только блокировка сборки мусора создает уведомления. Когда [ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) конфигурации элемент включен, фоновая сборка мусора не создает уведомления.  
  
 Чтобы определить, когда было выведено уведомление, используйте <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A> методы. Как правило, они используются в `while` цикла, чтобы постоянно получать <xref:System.GCNotificationStatus> перечисления, которое показывает состояние уведомления. Если это значение равно <xref:System.GCNotificationStatus.Succeeded>, можно сделать следующее:  
  
-   В ответ на уведомление, полученное с <xref:System.GC.WaitForFullGCApproach%2A> метод, можно перенаправить нагрузку и возможно вызвать сборку мусора самостоятельно.  
  
-   В ответ на уведомление, полученное с <xref:System.GC.WaitForFullGCComplete%2A> метод, можно сделать текущий экземпляр сервера, доступных для обработки запросов еще раз. Вы также можете собирать сведения. Например, можно использовать <xref:System.GC.CollectionCount%2A> метода для записи номера коллекций.  
  
 <xref:System.GC.WaitForFullGCApproach%2A> И <xref:System.GC.WaitForFullGCComplete%2A> методы предназначены для совместной работы. С помощью одного из них может привести к неопределенным результатам.  
  
## <a name="full-garbage-collection"></a>Полная сборка мусора  
 Полная сборка мусора средой выполнения, если выполняется одно из следующих сценариев:  
  
-   Недостаточно памяти в состояние поколения 2 сборки мусора следующего поколения 2.  
  
-   Недостаточно памяти в состояние кучи больших объектов для сборки мусора следующего поколения 2.  
  
-   Для поколения 1 перешла мусора поколения 2 из-за других факторов.  
  
 Пороговые значения, указанные в <xref:System.GC.RegisterForFullGCNotification%2A> метод применяются к первые два сценария. Однако в первом сценарии вы не всегда получит уведомление во время пропорционально пороговые значения, заданные по двум причинам:  
  
-   Среда выполнения не проверяет каждое выделение небольших объектов (по соображениям производительности).  
  
-   Только мусора поколения 1 переводит память в поколение 2.  
  
 Третий сценарий также объясняет неопределенность времени получения уведомления. Несмотря на то, что это не является гарантией его оказаться полезный способ устранить последствия неподходящие полную сборку мусора путем перенаправления запросов в течение этого времени или самостоятельного при лучше удовлетворяются.  
  
## <a name="notification-threshold-parameters"></a>Пороговые параметры уведомления  
 <xref:System.GC.RegisterForFullGCNotification%2A> Метод имеет два параметра, чтобы задать пороговые значения для объектов поколения 2 и кучи больших объектов. При соблюдении этих значений, должно вызываться уведомление о сборке мусора. В следующей таблице описаны эти параметры.  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Число от 1 до 99, указывающее условия уведомления на основе объектов, перешедших в поколение 2.|  
|`largeObjectHeapThreshold`|Число от 1 до 99, указывающее условия уведомления на основе объектов, выделенных в куче больших объектов.|  
  
 Если указать значение слишком велико, нет высокой степенью вероятности, вы получите уведомление, что это может быть долго ждать, пока среда выполнения вызовет сборку мусора. Если вы вызвать сборку мусора самостоятельно, можно освободить больше объектов, чем будет удален, если среда выполнения вызывает коллекции.  
  
 Если указать значение, которое слишком мало, среда выполнения может привести к коллекции до появления достаточное время, чтобы получать уведомления.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере группа серверов службы входящих веб-запросов. Для имитации рабочей нагрузки по обработке запросов, массивы байтов добавляются <xref:System.Collections.Generic.List%601> коллекции. Каждый сервер регистрирует уведомление о сборке мусора и запускает поток на `WaitForFullGCProc` пользовательского метода для постоянного наблюдения за <xref:System.GCNotificationStatus> перечисления, возвращенный <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A> методы.  
  
 <xref:System.GC.WaitForFullGCApproach%2A> И <xref:System.GC.WaitForFullGCComplete%2A> методы вызывать их соответствующие методы обработки событий пользователя при получении уведомления:  
  
-   `OnFullGCApproachNotify`  
  
     Этот метод вызывает метод `RedirectRequests` метод пользователя, который указывает, что серверу очереди приостановить отправку запросов на сервер. Это моделируется посредством задания переменной уровня класса `bAllocate` для `false` , чтобы дополнительные объекты не выделяются.  
  
     Далее, `FinishExistingRequests` вызывается пользовательский метод, чтобы завершить обработку запросов сервера. Это симуляции, сняв <xref:System.Collections.Generic.List%601> коллекции.  
  
     Наконец вызывается сборка мусора, поскольку нагрузка невелика.  
  
-   `OnFullGCCompleteNotify`  
  
     Этот метод вызывает пользовательский метод `AcceptRequests` возобновить прием запросов, поскольку сервер больше не подвержен атакам с полной сборкой мусора. Имитации этой операции, установив `bAllocate` переменной `true` , чтобы объекты можно возобновить, добавляемый <xref:System.Collections.Generic.List%601> коллекции.  
  
 Следующий код содержит `Main` метод примера.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 Следующий код содержит `WaitForFullGCProc` пользовательский метод, содержащий непрерывно цикл проверки о сборке мусора.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 Следующий код содержит `OnFullGCApproachNotify` метода, вызываемого из  
  
 Метод `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 Следующий код содержит `OnFullGCApproachComplete` метода, вызываемого из  
  
 Метод `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 В следующем коде содержатся методы пользователя, которые вызываются из `OnFullGCApproachNotify` и `OnFullGCCompleteNotify` методы. Пользовательские методы перенаправляют запросы, Готово существующие запросы и возобновите запросов после полной сборки мусора.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 Полный пример кода выглядит следующим образом:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Сборка мусора](../../../docs/standard/garbage-collection/index.md)
