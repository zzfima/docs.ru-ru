---
title: "Создание и запуск экземпляра рабочего процесса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b25acebfaf6df68ac3163a5ef4bcb235077139cc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="creating-and-running-a-workflow-instance"></a>Создание и запуск экземпляра рабочего процесса
В этом образце показано, как выполнить экземпляр рабочего процесса. Здесь показано синхронное и асинхронное выполнение.  
  
## <a name="demonstrates"></a>Демонстрации  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Обсуждение  
 В первой части образца используется метод <xref:System.Activities.WorkflowInvoker.Invoke%2A>. Это основной способ выполнения рабочего процесса. Рабочие процессы, запускаемые методом <xref:System.Activities.WorkflowInvoker.Invoke%2A>, выполняются синхронно.  
  
 Во второй части образца используется класс <xref:System.Activities.WorkflowApplication>. Класс <xref:System.Activities.WorkflowApplication> предоставляет дополнительные возможности управления каждым экземпляром, включая возможность взаимодействия с выполняющимся рабочим процессом и возможность асинхронного выполнения рабочего процесса.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>См. также  
 [Использование WorkflowInvoker и WorkflowApplication](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
