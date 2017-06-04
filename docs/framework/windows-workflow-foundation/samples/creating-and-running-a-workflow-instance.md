---
title: "Создание и запуск экземпляра рабочего процесса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Создание и запуск экземпляра рабочего процесса
В этом образце показано, как выполнить экземпляр рабочего процесса.Здесь показано синхронное и асинхронное выполнение.  
  
## Демонстрации  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## Обсуждение  
 В первой части образца используется метод <xref:System.Activities.WorkflowInvoker.Invoke%2A>.Это основной способ выполнения рабочего процесса.Рабочие процессы, запускаемые методом <xref:System.Activities.WorkflowInvoker.Invoke%2A>, выполняются синхронно.  
  
 Во второй части образца используется класс <xref:System.Activities.WorkflowApplication>.Класс <xref:System.Activities.WorkflowApplication> предоставляет дополнительные возможности управления каждым экземпляром, включая возможность взаимодействия с выполняющимся рабочим процессом и возможность асинхронного выполнения рабочего процесса.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## См. также  
 [Использование WorkflowInvoker и WorkflowApplication](../../../../docs/framework/windows-workflow-foundation//using-workflowinvoker-and-workflowapplication.md)