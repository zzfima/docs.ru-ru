---
title: Записи отслеживания
ms.date: 03/30/2017
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
ms.openlocfilehash: d59db7e4c90b3cffe523c89de093f58f3e520bde
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837614"
---
# <a name="tracking-records"></a>Записи отслеживания
Среда выполнения рабочего процесса инструментирована для создания записей отслеживания выполнения экземпляра рабочего процесса.  
  
## <a name="tracking-records"></a>Записи отслеживания  
 Следующая таблица содержит подробные сведения о записях отслеживания, создаваемых средой выполнения рабочего процесса.  
  
|Запись отслеживания|Описание|  
|---------------------|-----------------|  
|Записи жизненного цикла рабочего процесса|Создаются на различных этапах жизненного цикла экземпляра рабочего процесса. Например, запись создается при запуске и завершении рабочего процесса.|  
|Записи жизненного цикла действия|Подробные сведения о выполнении действия. Эти действия сообщают о состоянии действия рабочего процесса, например о планировании выполнения действия, о завершении действия или о возникновении ошибки.|  
|Записи возобновления закладок|Создается при возобновлении закладки в экземпляре рабочего процесса.|  
|Пользовательские записи отслеживания|Автор рабочего процесса может создавать настраиваемые записи отслеживания и выдавать их в рамках пользовательской операции.|  
  
 Все связанные с отслеживанием записи, созданные средой выполнения WF, являются производными от базового класса <xref:System.Activities.Tracking.TrackingRecord>, который содержит общий набор данных. Записи отслеживания отображают жизненный цикл простого рабочего процесса. Каждая запись отслеживания содержит сведения о соответствующем ей событии отслеживания, например <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>, <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A>, и дополнительные сведения, свойственные конкретному типу записи отслеживания.  
  
 Ниже приведены типы объектов <xref:System.Activities.Tracking.TrackingRecord>, которые создаются средой выполнения рабочего процесса:  
  
- **Воркфловинстанцерекорд** — этот <xref:System.Activities.Tracking.TrackingRecord> описывает жизненный цикл экземпляра рабочего процесса. Например, запись создается при запуске или завершении рабочего процесса и содержит состояние экземпляра рабочего процесса. Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceRecord>.  
  
- **Воркфловинстанцеабортедрекорд** — этот <xref:System.Activities.Tracking.TrackingRecord> создается при прерывании работы экземпляра рабочего процесса. Запись содержит причину прерывания экземпляра рабочего процесса. Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>.  
  
- **Воркфловинстанцеунхандледексцептионрекорд** — этот <xref:System.Activities.Tracking.TrackingRecord> создается, если исключение возникает в экземпляре рабочего процесса и не обрабатывается каким-либо действием. Запись содержит подробные сведения об исключении. Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>.  
  
- **WorkflowInstanceSuspendedRecord** — этот <xref:System.Activities.Tracking.TrackingRecord> создается каждый раз, когда экземпляр рабочего процесса приостанавливается. Запись содержит причину приостановки выполнения экземпляра рабочего процесса. Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>.  
  
- **Воркфловинстанцетерминатедрекорд** — этот <xref:System.Activities.Tracking.TrackingRecord> создается каждый раз, когда завершается работа экземпляра рабочего процесса. Запись содержит причину прекращения выполнения экземпляра рабочего процесса. Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>.  
  
- **Активитистатерекорд** — эта <xref:System.Activities.Tracking.TrackingRecord> создается при выполнении действия в рабочем процессе. Эти записи указывают состояние действия в экземпляре рабочего процесса. Сведения об этой записи приведены в <xref:System.Activities.Tracking.ActivityStateRecord>.  
  
- **Активитисчедуледрекорд** — этот <xref:System.Activities.Tracking.TrackingRecord> создается, когда действие планирует дочернее действие. Эта запись содержит подробные сведения о родительском действии (планирующем действии) и о запланированном дочернем действии. Сведения об этой записи приведены в <xref:System.Activities.Tracking.ActivityScheduledRecord>.  
  
- **Фаултпропагатионрекорд** — этот <xref:System.Activities.Tracking.TrackingRecord> создается для каждого обработчика, который просматривает запись до тех пор, пока не будет обработана. Используется для обозначения пути ошибки в экземпляре рабочего процесса. Сведения об этой записи приведены в <xref:System.Activities.Tracking.FaultPropagationRecord>.  
  
- **Канцелрекуестедрекорд** — этот <xref:System.Activities.Tracking.TrackingRecord> создается каждый раз, когда действие пытается отменить дочернее действие. Эта запись содержит подробные сведения о родительском действии и об отменяемом дочернем действии. Сведения об этой записи приведены в <xref:System.Activities.Tracking.CancelRequestedRecord>.  
  
- **Букмаркресумптионрекорд** — эта <xref:System.Activities.Tracking.TrackingRecord> отслеживает все успешно возобновление закладок. Сведения об этой записи приведены в <xref:System.Activities.Tracking.BookmarkResumptionRecord>.  
  
- **CustomTrackingRecord** — эта <xref:System.Activities.Tracking.TrackingRecord> создается и порождается автором рабочего процесса в рамках настраиваемого действия рабочего процесса. Пользовательские записи отслеживания можно заполнять данными, которые будут выдаваться вместе с записями. Сведения об этой записи приведены в <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
 Например, простое действие <xref:System.Activities.Statements.Sequence> может содержать операцию <xref:System.Activities.Statements.WriteLine> с записями отслеживания, выдаваемыми в следующем порядке.  
  
1. <xref:System.Activities.Tracking.WorkflowInstanceRecord> сообщает о запуске рабочего процесса.  
  
2. <xref:System.Activities.Tracking.ActivityScheduledRecord> сообщает, что запланировано действие. В данном случае этим действием является <xref:System.Activities.Statements.Sequence>.  
  
3. <xref:System.Activities.Tracking.ActivityScheduledRecord> представляет действие <xref:System.Activities.Statements.WriteLine>.  
  
4. Присутствуют две записи <xref:System.Activities.Tracking.ActivityStateRecord>, представляющие завершение двух действий.  
  
5. <xref:System.Activities.Tracking.WorkflowInstanceRecord> сообщает о завершении рабочего процесса.  
  
## <a name="see-also"></a>См. также:

- [Мониторинг Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Мониторинг приложений с помощью App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
