---
title: Использование отслеживания для устранения неполадок приложений
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: 1ed95a26f682fcdb609b410251fdb3f8b647016a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734426"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Использование отслеживания для устранения неполадок приложений
Windows Workflow Foundation (WF) позволяет отслеживать данные, относящихся к рабочему процессу, для последующей передачи подробных сведений в выполнение приложения Windows Workflow Foundation или службы. Узлы Windows Workflow Foundation, могут захватывать события рабочего процесса во время выполнения экземпляра рабочего процесса. Если в рабочем процессе возникают ошибки или исключения, можно использовать в Windows Workflow Foundation, отслеживание сведений для устранения неполадок обработки.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Устранение неполадок WF с помощью отслеживания WF  
 Для обнаружения ошибок при обработке действия Windows Workflow Foundation, можно включить отслеживание с профилем отслеживания, который запрашивает <xref:System.Activities.Tracking.ActivityStateRecord> в состоянии Faulted. Соответствующий запрос задан в следующем коде.  
  
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
  
 Когда экземпляр рабочего процесса обнаруживает необработанное исключение, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> объект создается в том случае, если включено отслеживание Windows Workflow Foundation.  
  
 Эта запись отслеживания содержит сведения об ошибке в виде стека исключений. Она содержит сведения об источнике ошибки (например, действие), которое и возникло необработанное исключение. Чтобы подписаться на события ошибок из Windows Workflow Foundation, включите отслеживание, добавив участника отслеживания. Настройте участника с профилем отслеживания, запрашивающим запись `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> и `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Если отслеживание включено с использованием участника отслеживания ETW, события ошибок создаются в сеансе ETW. События можно просмотреть с помощью средства «Просмотр событий». Его можно найти в узле **Просмотр событий -> Applications and Services Logs -> Майкрософт -> Windows -> сервер приложений-приложения** в канале аналитики.  
  
## <a name="see-also"></a>См. также
- [Мониторинг Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201273)
- [Мониторинг приложений с помощью фабрики приложения](https://go.microsoft.com/fwlink/?LinkId=201275)
