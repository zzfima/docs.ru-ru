---
title: "Действие в случае исключения «Экземпляр заблокирован»"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 164a5419-315c-4987-ad72-54cbdb88d402
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a5a0d805d5c8cbae67b97afa220ad769179e198
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="instance-locked-exception-action"></a>Действие в случае исключения «Экземпляр заблокирован»
Свойство <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> хранилища экземпляров рабочего процесса SQL позволяет указать, какое действие должен выполнить поставщик сохраняемости SQL при получении <xref:System.Runtime.DurableInstancing.InstanceLockedException>. Поставщик сохраняемости получает это исключение, когда пытается заблокировать экземпляр службы рабочего процесса, который в настоящий момент заблокирован другим узлом службы. Возможные значения этого свойства: <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>, <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> и <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>. Значение по умолчанию — <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>. В следующем списке приводится описание этих трех параметров.  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>. Узел службы не пытается заблокировать экземпляр службы рабочего процесса и передает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException> в вызывающий объект.  Если рабочий процесс остается в памяти в течение которых превышает 60 секунд, используйте <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry> как повторы. Значение по умолчанию — <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>.  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry>. Узел службы повторно пытается заблокировать экземпляр службы Workflow Service с линейными интервалами между попытками повтора и передает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException> вызывающему объекту в конце последовательности. Если рабочий процесс остается в памяти в течение приблизительно 5–60 секунд, а сообщения поступают пакетами, когда более вероятна отправка всех сообщений на обработку в один и тот же экземпляр на одном и том же узле до выгрузки рабочего процесса, используйте <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> для достижения оптимальной задержки без ненужной затраты ресурсов.  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>. Узел службы повторно пытается заблокировать экземпляр службы Workflow Service с экспоненциально растущим интервалом между попытками повтора и передает исключение вызывающему объекту в конце последовательности. Если рабочий процесс остается в памяти в течение очень короткого промежутка времени (менее 5 секунд) либо веб-ферма велика и вероятность доставки другого сообщения на тот же узел невелика, используйте <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry> для достижения оптимальной задержки.  
  
 Функция «Действие при возникновении исключения заблокированного экземпляра» поддерживает следующие сценарии. Во всех сценариях, если свойство instanceLockedExceptionAction хранилища SqlWorkflowInstanceStore имеет значение <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> или <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>, узел прозрачно выполняет периодические попытки заблокировать экземпляры.  
  
1.  **Включение правильное завершение работы и перезапуск с перекрытием для доменов приложений.** Предположим, что **AppDomain** с узлом службы экземпляров службы рабочего процесса выполняется повторно и создается новый **AppDomain** станет активным для обработки новых запросов параллельно старой  **AppDomain** корректно отключена. Завершение работы ожидает, пока все экземпляры служб рабочих процессов не войдут в неактивном состоянии, после чего сохраняет и выгружает экземпляры. Любые попытки узлов нового **AppDomain** заблокировать экземпляр вызовут <xref:System.Runtime.DurableInstancing.InstanceLockedException>.  
  
2.  **Горизонтальное масштабирование устойчивых рабочих процессов в гомогенной ферме серверов.** Предположим, что узел фермы серверов, на котором запущен экземпляр рабочего процесса, прекращает работу в результате сбоя и узел рабочего процесса не может снять блокировку запущенного экземпляра. Когда узел служб, запущенный на другом узле фермы, получает сообщение для этого экземпляра рабочего процесса, он пытается заблокировать экземпляры и получает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException>. Срок блокировки истечет через некоторое время, поскольку узел, который должен был обновить блокировку, уже не существует.  
  
     **Горизонтальное масштабирование устойчивых рабочих процессов в гомогенной ферме серверов.**  Предположим, что необходимо горизонтально масштабировать устойчивый рабочий процесс с использованием нескольких узлов сети балансировки нагрузки (NLB), узел рабочего процесса, работающий на одном узле фермы, загружает экземпляр рабочего процесса и обрабатывает сообщение, следующее сообщение экземпляру перенаправляется узел, на котором работает на другом узле, поскольку NLB не имеет алгоритма перенаправления сообщений на узел, на котором уже выполняется экземпляр. При получении сообщения второй узел пытается загрузить экземпляр рабочего процесса и получает исключение <xref:System.Runtime.DurableInstancing.InstanceLockedException>, поскольку первый узел уже заблокировал экземпляр. Первый узел снимает блокировку с экземпляра после завершения обработки первого сообщения, а второй узел получает блокировку во время второй попытки, загружает этот экземпляр и обрабатывает второе сообщение.
