---
title: "Использование отслеживания для устранения неполадок приложений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 02c6d346c6ebea27148c11f5f033f74dfb556e44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Использование отслеживания для устранения неполадок приложений
[!INCLUDE[wf](../../../includes/wf-md.md)] позволяет отслеживать данные, связанные с рабочим процессом, для последующей передачи подробных сведений в выполнение приложения [!INCLUDE[wf2](../../../includes/wf2-md.md)] или службы. Узлы [!INCLUDE[wf2](../../../includes/wf2-md.md)] могут захватывать события рабочего процесса во время выполнения экземпляра рабочего процесса. Если в рабочем процессе возникают ошибки или исключения, можно использовать данные отслеживания [!INCLUDE[wf2](../../../includes/wf2-md.md)] для устранения неполадок обработки.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Устранение неполадок WF с помощью отслеживания WF  
 Для обнаружения ошибок при обработке действия [!INCLUDE[wf2](../../../includes/wf2-md.md)] можно включить отслеживание с профилем отслеживания, в ходе которого запрашиваются записи <xref:System.Activities.Tracking.ActivityStateRecord> с состоянием ошибки (Faulted). Соответствующий запрос задан в следующем коде.  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 Если ошибка передается и обрабатывается в обработчике ошибок (например, в действии <xref:System.Activities.Statements.TryCatch>), это можно обнаружить с помощью записи <xref:System.Activities.Tracking.FaultPropagationRecord>. Запись <xref:System.Activities.Tracking.FaultPropagationRecord> указывает исходное действие, вызвавшее ошибку, и имя обработчика ошибок. Запись <xref:System.Activities.Tracking.FaultPropagationRecord> содержит сведения об ошибке в виде стека исключений для ошибки. Запрос на подписку на <xref:System.Activities.Tracking.FaultPropagationRecord> показан в следующем примере.  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 Если ошибка не обрабатывается в рабочем процессе, это создает необработанное исключение в экземпляре рабочего процесса, и работа экземпляра рабочего процесса прерывается. Для получения сведений о необработанном исключении профиль отслеживания должен запросить запись экземпляра рабочего процесса с состоянием `state name="UnhandledException"`, как указано в следующем примере.  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 Когда экземпляр рабочего процесса встречает необработанное исключение, создается объект <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>, если отслеживание [!INCLUDE[wf2](../../../includes/wf2-md.md)] включено.  
  
 Эта запись отслеживания содержит сведения об ошибке в виде стека исключений. Она содержит сведения об источнике ошибки (например, о действии), где произошел сбой, вызвавший необработанное исключение. Чтобы подписаться на события, связанные с ошибками, из [!INCLUDE[wf2](../../../includes/wf2-md.md)], включите отслеживание, добавив участника отслеживания. Настройте участника с профилем отслеживания, запрашивающим запись `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> и `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Если отслеживание включено с использованием участника отслеживания ETW, события ошибок создаются в сеансе ETW. События можно просмотреть с помощью средства «Просмотр событий». Это можно найти в узле **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения** в канале аналитики.  
  
## <a name="see-also"></a>См. также  
 [Наблюдение за Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Мониторинг приложений с](http://go.microsoft.com/fwlink/?LinkId=201275)
