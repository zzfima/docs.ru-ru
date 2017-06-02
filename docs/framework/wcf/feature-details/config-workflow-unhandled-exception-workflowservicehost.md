---
title: "Как настроить поведение необработанного исключения рабочего процесса при помощи WorkflowServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Как настроить поведение необработанного исключения рабочего процесса при помощи WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> — это поведение, которое позволяет указать действие, предпринимаемое при возникновении необработанного исключения в рабочем процессе, размещенном в <xref:System.ServiceModel.Activities.WorkflowServiceHost>.В этом разделе описано, как настроить поведение в файле конфигурации.  
  
### Настройка WorkflowUnhandledExceptionBehavior  
  
1.  Добавьте элемент \<`workflowUnhandledException`\> в элемент \<`behavior`\> внутрь элемента \<`serviceBehaviors`\>, с помощью атрибута `action` определив действие, предпринимаемое в случае возникновения необработанного исключения, как показано в следующем примере.  
  
    ```  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    ```  
  
    > [!NOTE]
    >  В предыдущем образце конфигурации используется упрощенная конфигурация.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Это поведение может быть настроено в коде, как показано в следующем примере.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
  
    ```  
  
     Атрибут `action` элемента \<`workflowUnhandledException`\> может быть установлен в одно из следующих значений.  
  
     **abandon**  
     Прерывает работу экземпляра в памяти без обращения к сохраненному состоянию экземпляра \(т.е. выполняет откат к последней сохраненной точке\).  
  
     **abandonAndSuspend**  
     Прерывает работу экземпляра в памяти и обновляет приостанавливаемый сохраненный экземпляр.  
  
     **cancel**  
     Вызывает отмену обработчиков экземпляра, а затем завершает работу экземпляра в памяти, что может удалить его из хранилища экземпляров.  
  
     **terminate**  
     Завершает работу экземпляра в памяти и удаляет его из хранилища экземпляров.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] о <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> см. в разделе [Расширяемость узла службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## См. также  
 [Расширяемость узла службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)   
 [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)