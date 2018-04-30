---
title: Как настроить поведение необработанного исключения рабочего процесса при помощи WorkflowServiceHost
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a49b3d42e51ed7a0a57deb392f5728f407909b00
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Как настроить поведение необработанного исключения рабочего процесса при помощи WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> - это поведение, которое позволяет указать действие, предпринимаемое при возникновении необработанного исключения в рабочем процессе, размещенном в <xref:System.ServiceModel.Activities.WorkflowServiceHost>. В этом разделе описано, как настроить поведение в файле конфигурации.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>Настройка WorkflowUnhandledExceptionBehavior  
  
1.  Добавить <`workflowUnhandledException`> элемента <`behavior`> элемент в пределах <`serviceBehaviors`> элемент, с помощью `action` атрибут, чтобы задать действие, предпринимаемое при возникновении необработанного исключения, как показано в следующем примере.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  В предыдущем образце конфигурации используется упрощенная конфигурация. Дополнительные сведения см. в разделе [упрощенной конфигурации](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Это поведение может быть настроено в коде, как показано в следующем примере.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     `action` Атрибут <`workflowUnhandledException`> элемент может быть присвоено одно из следующих значений:  
  
     **Прерывания**  
     Прерывает работу экземпляра в памяти без обращения к сохраненному состоянию экземпляра (т.е. выполняет откат к последней сохраненной точке).  
  
     **abandonAndSuspend**  
     Прерывает работу экземпляра в памяти и обновляет приостанавливаемый сохраненный экземпляр.  
  
     **Отмена**  
     Вызывает отмену обработчиков экземпляра, а затем завершает работу экземпляра в памяти, что может удалить его из хранилища экземпляров.  
  
     **terminate**  
     Завершает работу экземпляра в памяти и удаляет его из хранилища экземпляров.  
  
     Дополнительные сведения о <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, в разделе [расширяемость узла службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>См. также  
 [Расширяемость узла службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)
