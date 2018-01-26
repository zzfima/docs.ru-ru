---
title: "Отслеживание и трассировка рабочих процессов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], tracking and tracing
ms.assetid: b965ded6-370a-483d-8790-f794f65b137e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7383d899af741e4a6c85b40e2316a6b759aa416
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-tracking-and-tracing"></a>Отслеживание и трассировка рабочих процессов
Отслеживание рабочих процессов Windows является функцией [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)], разработанной для обеспечения возможности отслеживания выполнения рабочих процессов. Она обеспечивает инфраструктуру отслеживания выполнения экземпляра рабочего процесса. Инфраструктура отслеживания WF прозрачно инструментирует рабочий процесс таким образом, что выдаются записи, отражающие ключевые события выполнения. Эта функция доступна по умолчанию для всех рабочих процессов [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. Для выполнения отслеживания в рабочий процесс [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] не нужно вносить изменения. Необходимо лишь определить объем данных отслеживания, которые требуется получать. При запуске или завершении экземпляра рабочего процесса создаются записи отслеживания, которые затем обрабатываются. Отслеживание также позволяет извлекать важные для бизнеса данные, связанные с переменными рабочего процесса. Например, если рабочий процесс представляет собой систему обработки заказов, вместе с объектом <xref:System.Activities.Tracking.TrackingRecord> можно извлечь идентификатор заказа. Как правило, функции отслеживания WF позволяют упростить диагностику и доступ к данным бизнес-аналитики из выполняемого рабочего процесса.  
  
 Эти компоненты отслеживания эквивалентны службе отслеживания в [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)]. [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] отличается более высоким уровнем производительности, а модель программирования для функции отслеживания WF - более простая. Среды выполнения отслеживания инструментирует экземпляр рабочего процесса для создания событий, связанных с жизненным циклом рабочего процесса, действиями рабочего процесса и настраиваемыми событиями.  
  
 Windows Server App Fabric также дает возможность наблюдать за выполнением WCF и службы Workflow Service. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Мониторинга Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273) и [мониторинг приложений с Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201287)  
  
 Чтобы провести диагностику среды выполнения рабочего процесса, можно включить трассировку рабочего процесса диагностики. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Трассировка рабочего процесса](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md).  
  
 В этом разделе описаны основные компоненты инфраструктуры отслеживания, которые позволяют понять принципы работы модели программирования:  
  
-   Объекты <xref:System.Activities.Tracking.TrackingRecord>, создаваемые во время выполнения рабочего процесса. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Записи отслеживания](../../../docs/framework/windows-workflow-foundation/tracking-records.md).  
  
-   Объекты <xref:System.Activities.Tracking.TrackingParticipant> подписываются на объекты <xref:System.Activities.Tracking.TrackingRecord>. Участники отслеживания содержат логику обработки полезных данных из объектов <xref:System.Activities.Tracking.TrackingRecord> (например, они могут записывать данные в файл). [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Участникам отслеживания](../../../docs/framework/windows-workflow-foundation/tracking-participants.md).  
  
-   Записи отслеживания фильтра объекта <xref:System.Activities.Tracking.TrackingProfile>, создаваемые экземпляром рабочего процесса. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Профили отслеживания](../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
## <a name="workflow-tracking-infrastructure"></a>Инфраструктура отслеживания рабочих процессов  
 Инфраструктура отслеживания рабочего процесса основана на принципе публикации и подписки. Экземпляр рабочего процесса является издателем записей отслеживания, а подписчики записей отслеживания регистрируются как расширения рабочего процесса. Эти расширения, подписанные на объекты <xref:System.Activities.Tracking.TrackingRecord>, называются участниками отслеживания. Участниками отслеживания являются точки расширения, обращающиеся к объектам <xref:System.Activities.Tracking.TrackingRecord> и обрабатывающие их с использованием заданных для них способов. Инфраструктура отслеживания позволяет применять к исходящим записям отслеживания фильтр таким образом, что участник может подписаться на определенное подмножество записей. Механизм фильтрации реализуется с помощью файла профиля отслеживания.  
  
 На следующем рисунке показано высокоуровневое представление инфраструктуры отслеживания.  
  
 ![Инфраструктура отслеживания рабочего процесса](../../../docs/framework/windows-workflow-foundation/media/wv.gif "WV")  
  
## <a name="in-this-section"></a>В этом разделе  
 [Записи отслеживания](../../../docs/framework/windows-workflow-foundation/tracking-records.md)  
 Описывает записи отслеживания, создаваемые средой выполнения рабочего процесса.  
  
 [Профили отслеживания](../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
 Описывает использование профилей отслеживания.  
  
 [Участники отслеживания](../../../docs/framework/windows-workflow-foundation/tracking-participants.md)  
 Описывает использование предоставленных системой участников отслеживания и создание настраиваемых участников отслеживания.  
  
 [Настройка отслеживания рабочего процесса](../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)  
 Описывает настройку отслеживания рабочего процесса.  
  
 [Трассировка рабочих процессов](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 Описывает два способа включения трассировки отладки рабочего процесса.  
  
 [Использование трассировки для определения длительности выполнения рабочего процесса](../../../docs/framework/windows-workflow-foundation/determining-workflow-execution-duration-using-tracing.md)  
 Описывает, как использовать сообщения трассировки для определения продолжительности выполнения рабочего процесса.  
  
## <a name="see-also"></a>См. также  
 [Отслеживание SQL](../../../docs/framework/windows-workflow-foundation/samples/sql-tracking.md)
