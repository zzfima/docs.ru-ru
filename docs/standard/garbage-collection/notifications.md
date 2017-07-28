---
title: "Garbage Collection Notifications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "garbage collection, notifications"
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Garbage Collection Notifications
В некоторых случаях полная сборка мусора \(сборка объектов поколения 2\) средой CLR может отрицательно сказаться на производительности.  Такая ситуация особенно часто возникает применительно к серверам, которые обрабатывают большие объемы запросов; в этом случае долгая процедура сборки мусора может вызывать задержку обработки запроса.  Чтобы избежать сборки мусора в критический интервал времени, можно использовать уведомления о приближающейся сборке мусора и принимать меры по перенаправлению нагрузки на другой экземпляр сервера.  Кроме того, можно самостоятельно вызвать сборку мусора, если не требуется обрабатывать запросы с помощью текущего экземпляра сервера.  
  
 Метод <xref:System.GC.RegisterForFullGCNotification%2A> регистрируется для создания уведомления, когда среда выполнения получает информацию о том, что вскоре начнется сборка мусора.  Это уведомление состоит из двух частей — о приближающейся сборке мусора и о завершенной сборке мусора.  
  
> [!WARNING]
>  Только блокировка сборки мусора порождает уведомления.  Если элемент конфигурации [\<gcConcurrent\>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) будет включен, фоновая сборки мусора не будет порождать уведомления.  
  
 Чтобы определить вариант уведомления, следует использовать методы <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A>.  Обычно они используются в цикле `while`, чтобы постоянно получать перечисление <xref:System.GCNotificationStatus>, содержащее информацию о состоянии уведомления.  Если перечисление имеет значение <xref:System.GCNotificationStatus>, можно выполнить следующие действия.  
  
-   В ответ на уведомление, полученное с помощью метода <xref:System.GC.WaitForFullGCApproach%2A>, можно перенаправить нагрузку или попытаться самостоятельно вызвать сборку мусора.  
  
-   В ответ на уведомление, полученное с помощью метода <xref:System.GC.WaitForFullGCComplete%2A>, можно сделать текущий экземпляр сервера снова доступным для обработки запросов.  Кроме того, можно собирать информацию.  Например, с помощью метода <xref:System.GC.CollectionCount%2A> можно фиксировать количество процедур сборки мусора.  
  
 Методы <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A> должны использоваться вместе.  Применение только одного из них может привести к непредсказуемым результатам.  
  
## Полная сборка мусора  
 Среда выполнения запускает полную сборку мусора в следующих случаях.  
  
-   В состояние поколения 2 перешел объем памяти, достаточный для сборки мусора следующего поколения 2.  
  
-   В состояние кучи больших объектов перешел объем памяти, достаточный для сборки мусора следующего поколения 2.  
  
-   Сборка мусора поколения 1 перешла в сборку мусора поколения 2 по другим причинам.  
  
 Указываемые в методе <xref:System.GC.RegisterForFullGCNotification%2A> пороговые значения относятся к первым двум случаям.  Однако в первом случае необходимо всегда получать уведомления за время, пропорциональное заданным пороговым значениями. На это есть две причины.  
  
-   Среда выполнения не проверяет выделение памяти для каждого небольшого объекта \(по соображениям производительности\).  
  
-   Только сборка мусора поколения 1 переводит память в поколение 2.  
  
 Третий случай также объясняет неопределенность времени получения уведомления.  Хотя этот способ и не дает стопроцентной гарантии, он оказывается достаточно эффективным для минимизации последствий несвоевременной сборки мусора путем перенаправления запросов на это время или самостоятельного вызова сборки в более удобное время.  
  
## Пороговые параметры уведомления  
 У метода <xref:System.GC.RegisterForFullGCNotification%2A> имеется два параметра для задания пороговых значений объектов поколения 2 и кучи больших объектов.  Уведомление создается в тот момент, когда достигаются эти значения.  Данные параметры описаны в следующей таблице.  
  
|Параметр|Описание|  
|--------------|--------------|  
|`maxGenerationThreshold`|Число от 1 до 99, указывающее условия создания уведомления в зависимости от объектов, перешедших в поколение 2.|  
|`largeObjectHeapThreshold`|Число от 1 до 99, указывающее условия создания уведомления в зависимости от объектов, помещенных в кучу больших объектов.|  
  
 Если указать слишком большое значение, то вероятность получения уведомления будет высокой, однако придется долго ждать, пока среда выполнения вызовет сборку мусора.  Если вызвать сборку мусора самостоятельно, можно освободить больше объектов, чем было бы освобождено при запуске сборки мусора средой выполнения.  
  
 Если указать слишком маленькое значение, среда выполнения может вызвать сборку мусора раньше получения уведомления.  
  
## Пример  
  
### Описание  
 В следующем примере группа серверов обрабатывает входящие веб\-запросы.  Чтобы имитировать нагрузку, создаваемую при обработке запросов, в коллекцию <xref:System.Collections.Generic.List%601> добавляются массивы байтов.  Каждый сервер регистрируется на получение уведомления о сборке мусора и запускает поток для метода пользователя `WaitForFullGCProc`, чтобы постоянно контролировать значение перечисления <xref:System.GCNotificationStatus>, возвращаемого методами <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A>.  
  
 При получении уведомления методы <xref:System.GC.WaitForFullGCApproach%2A> и <xref:System.GC.WaitForFullGCComplete%2A> запускают соответствующие пользовательские методы для обработки событий.  
  
-   `OnFullGCApproachNotify`  
  
     Этот метод вызывает пользовательский метод `RedirectRequests`, который отдает серверу очереди команду приостановить отправку запросов на данный сервер.  Для имитации такой ситуации переменной уровня класса `bAllocate` присваивается значение `false`, чтобы память для новых объектов не выделялась.  
  
     Затем вызывается пользовательский метод `FinishExistingRequests`, который завершает обработку находящихся в очереди запросов сервера.  Для имитации этой ситуации коллекция <xref:System.Collections.Generic.List%601> очищается.  
  
     Наконец, вызывается сборка мусора, поскольку нагрузка невелика.  
  
-   `OnFullGCCompleteNotify`  
  
     Этот метод вызывает пользовательский метод `AcceptRequests`, чтобы возобновить прием запросов, поскольку сервер больше не ожидает полной сборки мусора.  Для имитации этой операции переменной `bAllocate` присваивается значение `true`, чтобы возобновить добавление объектов в коллекцию <xref:System.Collections.Generic.List%601>.  
  
 Ниже показан код метода `Main` этого примера.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 Ниже показан код пользовательского метода `WaitForFullGCProc`, содержащий выполняющийся непрерывно цикл проверки уведомлений о сборке мусора.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 Ниже показан код метода `OnFullGCApproachNotify`, вызываемого из метода  
  
 `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 Ниже показан код метода `OnFullGCApproachComplete`, вызываемого из метода  
  
 `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 Ниже показан код пользовательских методов, вызываемых из методов `OnFullGCApproachNotify` и `OnFullGCCompleteNotify`.  Пользовательские методы перенаправляют запросы, завершают обработку уже полученных запросов и возобновляют прием запросов по завершении полной сборки мусора.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 Ниже приведен код всего примера.  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## См. также  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)