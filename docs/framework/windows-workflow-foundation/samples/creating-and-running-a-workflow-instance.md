---
title: Создание и запуск экземпляра рабочего процесса
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: 571d41194ebc98be81646fb5bfdab060225015ca
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964412"
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>См. также  
 [Использование WorkflowInvoker и WorkflowApplication](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
