---
title: "Записи отслеживания | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51adbda3-bd8b-4892-a8ea-d343186472d2
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Записи отслеживания
Среда выполнения рабочего процесса инструментирована для создания записей отслеживания выполнения экземпляра рабочего процесса.  
  
## Записи отслеживания  
 Следующая таблица содержит подробные сведения о записях отслеживания, создаваемых средой выполнения рабочего процесса.  
  
|Запись отслеживания|Описание|  
|-------------------------|--------------|  
|Записи жизненного цикла рабочего процесса|Создаются на различных этапах жизненного цикла экземпляра рабочего процесса.Например, запись создается при запуске и завершении рабочего процесса.|  
|Записи жизненного цикла действия|Подробные сведения о выполнении действия.Эти действия сообщают о состоянии действия рабочего процесса, например о планировании выполнения действия, о завершении действия или о возникновении ошибки.|  
|Запись возобновления закладки|Создается при возобновлении закладки в экземпляре рабочего процесса.|  
|Пользовательские записи отслеживания|Автор рабочего процесса может создавать настраиваемые записи отслеживания и выдавать их в рамках пользовательской операции.|  
  
 Все связанные с отслеживанием записи, созданные средой выполнения WF, являются производными от базового класса <xref:System.Activities.Tracking.TrackingRecord>, который содержит общий набор данных.Записи отслеживания отображают жизненный цикл простого рабочего процесса.Каждая запись отслеживания содержит сведения о соответствующем ей событии отслеживания, например <xref:System.Activities.Tracking.TrackingRecord.InstanceId%2A>, <xref:System.Activities.Tracking.TrackingRecord.RecordNumber%2A>, и дополнительные сведения, свойственные конкретному типу записи отслеживания.  
  
 Ниже приведены типы объектов <xref:System.Activities.Tracking.TrackingRecord>, которые создаются средой выполнения рабочего процесса:  
  
-   **WorkflowInstanceRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> описывает жизненный цикл экземпляра рабочего процесса.Например, запись создается при запуске или завершении рабочего процесса и содержит состояние экземпляра рабочего процесса.Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceRecord>.  
  
-   **WorkflowInstanceAbortedRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается при прерывании экземпляра рабочего процесса.Запись содержит причину прерывания экземпляра рабочего процесса.Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>.  
  
-   **WorkflowInstanceUnhandledExceptionRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается при возникновении исключения в экземпляре рабочего процесса, не обработанного ни одним из действий.Запись содержит подробные сведения об исключении.Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>.  
  
-   **WorkflowInstanceSuspendedRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается при приостановке выполнения экземпляра рабочего процесса.Запись содержит причину приостановки выполнения экземпляра рабочего процесса.Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>.  
  
-   **WorkflowInstanceTerminatedRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается при прекращении выполнения экземпляра рабочего процесса.Запись содержит причину прекращения выполнения экземпляра рабочего процесса.Сведения об этой записи приведены в <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>.  
  
-   **ActivityStateRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается при выполнении действия в рабочем процессе.Эти записи указывают состояние действия в экземпляре рабочего процесса.Сведения об этой записи приведены в <xref:System.Activities.Tracking.ActivityStateRecord>.  
  
-   **ActivityScheduledRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается при планировании действием дочернего действия.Эта запись содержит подробные сведения о родительском действии \(планирующем действии\) и о запланированном дочернем действии.Сведения об этой записи приведены в <xref:System.Activities.Tracking.ActivityScheduledRecord>.  
  
-   **FaultPropagationRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается для каждого обработчика, просматривающего запись до ее обработки.Используется для обозначения пути ошибки в экземпляре рабочего процесса.Сведения об этой записи приведены в <xref:System.Activities.Tracking.FaultPropagationRecord>.  
  
-   **CancelRequestedRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается, когда действие пытается отменить дочернее действие.Эта запись содержит подробные сведения о родительском действии и об отменяемом дочернем действии.Сведения об этой записи приведены в <xref:System.Activities.Tracking.CancelRequestedRecord>.  
  
-   **BookmarkResumptionRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> отслеживает любую успешно восстановленную закладку.Сведения об этой записи приведены в <xref:System.Activities.Tracking.BookmarkResumptionRecord>.  
  
-   **CustomTrackingRecord**: эта запись <xref:System.Activities.Tracking.TrackingRecord> создается и выдается автором рабочего процесса в пользовательском действии рабочего процесса.Пользовательские записи отслеживания можно заполнять данными, которые будут выдаваться вместе с записями.Сведения об этой записи приведены в <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
 Например, простое действие <xref:System.Activities.Statements.Sequence> может содержать операцию <xref:System.Activities.Statements.WriteLine> с записями отслеживания, выдаваемыми в следующем порядке:  
  
1.  <xref:System.Activities.Tracking.WorkflowInstanceRecord> сообщает о запуске рабочего процесса.  
  
2.  <xref:System.Activities.Tracking.ActivityScheduledRecord> сообщает, что запланировано действие.В данном случае этим действием является <xref:System.Activities.Statements.Sequence>.  
  
3.  <xref:System.Activities.Tracking.ActivityScheduledRecord> представляет действие <xref:System.Activities.Statements.WriteLine>.  
  
4.  Присутствуют две записи <xref:System.Activities.Tracking.ActivityStateRecord>, представляющие завершение двух действий.  
  
5.  <xref:System.Activities.Tracking.WorkflowInstanceRecord> сообщает о завершении рабочего процесса.  
  
## См. также  
 [Наблюдение за фабрикой приложений сервера Windows](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Наблюдение за приложениями с помощью фабрики приложения](http://go.microsoft.com/fwlink/?LinkId=201275)