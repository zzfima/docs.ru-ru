---
title: "События трассировки событий Windows в библиотеке параллельных задач и PLINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "задачи, события трассировки событий Windows"
ms.assetid: 87a9cff5-d86f-4e44-a06e-d12764d0dce2
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# События трассировки событий Windows в библиотеке параллельных задач и PLINQ
Библиотека параллельных задач и PLINQ создают события трассировки событий Windows \(ETW\), которые можно использовать для профилирования и диагностики приложений с помощью таких средств, как Windows Performance Analyzer.  Тем не менее в большинстве сценариев оптимальный способ профилировки параллельного кода приложения — это использование [Визуализатор параллелизма](../Topic/Concurrency%20Visualizer.md) из [!INCLUDE[vsUltShort](../../../includes/vsultshort-md.md)].  
  
## События трассировки событий Windows в библиотеке параллельных задач  
 В структуре EVENT\_HEADER идентификатор GUID ProviderId для событий, создаваемых методами <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> и <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=fullName>, задается следующим образом:  
  
```  
0x2e5dba47, 0xa3d2, 0x4d16, 0x8e, 0xe0, 0x66, 0x71, 0xff, 0xdc, 0xd7, 0xb5  
```  
  
### Начало параллельного цикла  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### Данные пользователя  
  
|**Имя**|**Тип**|**Описание**|  
|-------------|-------------|------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Идентификатор TaskScheduler, начавшего цикл.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Идентификатор задачи, начавшей цикл.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|Для обозначения вложений и пар для событий с семантикой разветвлений и соединений используется уникальный идентификатор.|  
|OperationType|<xref:System.Int32?displayProperty=fullName>|Указывает тип цикла:<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|InclusiveFrom|<xref:System.Int64?displayProperty=fullName>|Начальное значение счетчика цикла|  
|ExclusiveTo|<xref:System.Int64?displayProperty=fullName>|Конечное значение счетчика цикла|  
  
### Конец параллельного цикла  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### Данные пользователя  
  
|**Имя**|**Тип**|**Описание**|  
|-------------|-------------|------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Идентификатор TaskScheduler, начавшего цикл.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Идентификатор задачи, начавшей цикл.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|Для обозначения вложений и пар для событий с семантикой разветвлений и соединений используется уникальный идентификатор.|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|Общее число итераций|  
  
### Начало параллельного вызова  
 EVENT\_DESCRIPTOR.Task \= 3  
  
 EVENT\_DESCRIPTOR.Id \= 3  
  
#### Данные пользователя  
  
|**Имя**|**Тип**|**Описание**|  
|-------------|-------------|------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Идентификатор TaskScheduler, начавшего цикл.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Идентификатор задачи, начавшей цикл.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|Для обозначения вложений и пар для событий с семантикой разветвлений и соединений используется уникальный идентификатор.|  
|totalIterations|<xref:System.Int64?displayProperty=fullName>|Общее число итераций|  
|operationType|<xref:System.Int32?displayProperty=fullName>|Указывает тип цикла:<br /><br /> 1 \= ParallelInvoke<br /><br /> 2 \= ParallelFor<br /><br /> 3 \= ParallelForEach|  
|ActionCount|<xref:System.Int32?displayProperty=fullName>|Количество действий, которые будут выполнены при параллельном вызове.|  
  
### Конец параллельного вызова  
 EVENT\_DESCRIPTOR.Task \= 4  
  
 EVENT\_DESCRIPTOR.Id \= 4  
  
#### Данные пользователя  
  
|**Имя**|**Тип**|**Описание**|  
|-------------|-------------|------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Идентификатор TaskScheduler, начавшего цикл.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Идентификатор задачи, начавшей цикл.|  
|ForkJoinContextID|<xref:System.Int32?displayProperty=fullName>|Для обозначения вложений и пар для событий с семантикой разветвлений и соединений используется уникальный идентификатор.|  
  
## События трассировки событий Windows для PLINQ  
 Идентификатор GUID EVENT\_HEADER.ProviderId для PLINQ:  
  
```  
0x159eeeec, 0x4a14, 0x4418, 0xa8, 0xfe, 0xfa, 0xab, 0xcd, 0x98, 0x78, 0x87  
```  
  
### Начало параллельного запроса  
 EVENT\_DESCRIPTOR.Task \= 1  
  
 EVENT\_DESCRIPTOR.Id \= 1  
  
#### Данные пользователя  
  
|**Имя**|**Тип**|**Описание**|  
|-------------|-------------|------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Идентификатор TaskScheduler, начавшего цикл.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Идентификатор задачи, начавшей цикл.|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|Уникальный идентификатор запроса.|  
  
### Конец параллельного запроса  
 EVENT\_DESCRIPTOR.Task \= 2  
  
 EVENT\_DESCRIPTOR.Id \= 2  
  
#### Данные пользователя  
  
|**Имя**|**Тип**|**Описание**|  
|-------------|-------------|------------------|  
|OriginatingTaskSchedulerID|<xref:System.Int32?displayProperty=fullName>|Идентификатор TaskScheduler, начавшего цикл.|  
|OriginatingTaskID|<xref:System.Int32?displayProperty=fullName>|Идентификатор задачи, начавшей цикл.|  
|QueryID|<xref:System.Int32?displayProperty=fullName>|Уникальный идентификатор запроса.|  
  
## См. также  
 [ETW Events in the .NET Framework](../../../docs/framework/performance/etw-events.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)