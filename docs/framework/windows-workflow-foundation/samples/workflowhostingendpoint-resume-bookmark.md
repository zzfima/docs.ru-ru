---
title: "Закладка возобновления для конечной точки WorkflowHostingEndpoint"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc3c92245a641b42b0357f9c6dd536dccacd6496
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="workflowhostingendpoint-resume-bookmark"></a>Закладка возобновления для конечной точки WorkflowHostingEndpoint
В этом образце показано использование <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> с <xref:System.ServiceModel.Activities.WorkflowServiceHost> для создания экземпляров рабочего процесса.  
  
## <a name="demonstrates"></a>Демонстрации  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a>Обсуждение  
 Этот образец использует <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> для создания экземпляра рабочего процесса, размещенного с помощью <xref:System.ServiceModel.Activities.WorkflowServiceHost>. <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> - точка расширения для <xref:System.ServiceModel.Activities.WorkflowServiceHost>, которую можно использовать в следующих сценариях:  
  
-   Создание новых экземпляров рабочего процесса.  
  
-   Возобновление закладок в экземпляре рабочего процесса, размещенного на узле <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
 Включенный образец конечной точки предоставляет контракт на выполнение операций, которые создают рабочий процесс и возвращают идентификатор экземпляра или создают экземпляр с конкретным идентификатором. В приведенном образце консольного приложения создается экземпляр <xref:System.ServiceModel.Activities.WorkflowServiceHost> с базовым определением рабочего процесса, и к узлу добавляется конечная точка `CreationEndpoint`. Затем в конечной точке вызывается операция `Create`, чтобы создать новый экземпляр рабочего процесса.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Постройте решение.  
  
2.  Запустите приложение. При создании экземпляра рабочего процесса на консоли `CreationEndpoint` выводится сообщение, содержащее идентификатор экземпляра. Сообщение «Hello World!» выводится после успешного возобновления закладки рабочим процессом.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
