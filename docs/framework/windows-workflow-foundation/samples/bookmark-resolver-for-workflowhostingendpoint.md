---
title: "Арбитр закладок для конечной точки WorkflowHostingEndpoint | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Арбитр закладок для конечной точки WorkflowHostingEndpoint
В этом образце показано использование <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> с <xref:System.ServiceModel.Activities.WorkflowServiceHost> для создания экземпляров рабочего процесса.  
  
## Демонстрации  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## Обсуждение  
 Этот образец использует <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> для создания экземпляров рабочих процессов, размещенных с помощью <xref:System.ServiceModel.Activities.WorkflowServiceHost>.<xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> — это точка расширения для <xref:System.ServiceModel.Activities.WorkflowServiceHost>, которую можно использовать в следующих сценариях.  
  
-   Создание новых экземпляров рабочего процесса.  
  
-   Возобновление закладок в экземпляре рабочего процесса, размещенного в <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
 В приведенном образце точки расширения представлен контракт на выполнение операций, создающих рабочий процесс и возвращающих идентификатор экземпляра или создающих экземпляр с конкретным идентификатором.В приведенном образце консольного приложения создается экземпляр <xref:System.ServiceModel.Activities.WorkflowServiceHost>, определяющий рабочий процесс, и к узлу добавляется `CreationEndpoint`.Затем в конечной точке вызывается операция `Create`, чтобы создать новый экземпляр рабочего процесса.  
  
#### Настройка, построение и выполнение образца  
  
1.  Постройте решение.  
  
2.  Запустите приложение.При создании экземпляра рабочего процесса на консоли `CreationEndpoint` выводится сообщение, содержащее идентификатор экземпляра.Экземпляр рабочего процесса выводит на консоль сообщение "Hello World\!".  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`