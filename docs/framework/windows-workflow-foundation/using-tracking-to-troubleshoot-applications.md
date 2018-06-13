---
title: Использование отслеживания для устранения неполадок приложений
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: ee9aaaae80f213f026a222ac1754ae8b4fdf2d37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517047"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Использование отслеживания для устранения неполадок приложений
Windows Workflow Foundation (WF) позволяет отслеживать сведения о рабочем процессе для предоставления сведений в выполнение Windows Workflow Foundation приложения или службы. Узлы Windows Workflow Foundation, могут захватывать события рабочего процесса во время выполнения экземпляра рабочего процесса. Если рабочий процесс приводит к возникновению ошибки или исключения, можно использовать данные отслеживания для устранения неполадок обработки Windows Workflow Foundation.  
  
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
  
 Когда экземпляр рабочего процесса обнаруживается необработанное исключение, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> объект создается в том случае, если включено отслеживание Windows Workflow Foundation.  
  
 Эта запись отслеживания содержит сведения об ошибке в виде стека исключений. Она содержит сведения об источнике ошибки (например, действие), произошел сбой, вызвавший необработанное исключение. Чтобы подписаться на события ошибок с Windows Workflow Foundation, включите отслеживание путем добавления участника отслеживания. Настройте участника с профилем отслеживания, запрашивающим запись `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> и `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Если отслеживание включено с использованием участника отслеживания ETW, события ошибок создаются в сеансе ETW. События можно просмотреть с помощью средства «Просмотр событий». Это можно найти в узле **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения** в канале аналитики.  
  
## <a name="see-also"></a>См. также  
 [Наблюдение за Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Мониторинг приложений с](http://go.microsoft.com/fwlink/?LinkId=201275)
