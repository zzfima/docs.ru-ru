---
title: "Образец конечной точки управления рабочим процессом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e516d41a9f9736877fb3974774ddaf4b3bddb198
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-management-endpoint-sample"></a>Образец конечной точки управления рабочим процессом
Этот образец показывает, как можно использовать конечную точку управления рабочего процесса для создания и запуска рабочих процессов как локально, так и удаленно. В следующем образце показано создание узла конечной точки управления, и клиентов, вызывающих конечную точку управления для создания и запуска экземпляра рабочего процесса. Рабочий процесс не является службой.  
  
 На стороне службы образца рабочий процесс размещен с помощью WorkflowServiceHost, а также добавлен WorkflowControlEndpoint, что позволяет клиентам выполнять операции управления (приостановка, запуск и т. д.). Добавлено также определяемое пользователем создание конечной точки CreationEndpoint, что позволяет создать рабочий процесс. Затем служба использует эти конечные точки для запуска рабочего процесса в приостановленном состоянии, а после этого возобновляет рабочий процесс. Клиент выполняет те же операции, но в коде клиента. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]просмотреть эти интерфейсы, [конечной точки управления рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) и [как: разместить не являющийся службой рабочий процесс в службах IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Запустите среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с правами администратора.  
  
2.  Откройте решение ManagementEndpoint.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Чтобы построить решение, нажмите клавиши CTRL + SHIFT + B или выберите **построить решение** из **построения** меню.  
  
4.  Запустите приложение ManagementEndpoint.exe.  
  
5.  Запустите приложение Client.exe.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`