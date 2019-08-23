---
title: Практическое руководство. Как настроить поведение необработанного исключения рабочего процесса при помощи WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: aec2fd80e10ae1959b29c0883d51c4045517d792
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957262"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Практическое руководство. Как настроить поведение необработанного исключения рабочего процесса при помощи WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> - это поведение, которое позволяет указать действие, предпринимаемое при возникновении необработанного исключения в рабочем процессе, размещенном в <xref:System.ServiceModel.Activities.WorkflowServiceHost>. В этом разделе описано, как настроить поведение в файле конфигурации.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>Настройка WorkflowUnhandledExceptionBehavior  
  
1. Добавьте элемент <`workflowUnhandledException`> в элемент <`behavior`> в элементе <`serviceBehaviors`> с помощью `action` атрибута, чтобы указать действие, выполняемое при возникновении необработанного исключения, как показано в следующем примере.  
  
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
    > В предыдущем образце конфигурации используется упрощенная конфигурация. Дополнительные сведения см. в разделе [упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Это поведение может быть настроено в коде, как показано в следующем примере.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     Атрибуту элемента <`workflowUnhandledException`> можно присвоить одно из следующих значений: `action`  
  
     **прерывания**  
     Прерывает работу экземпляра в памяти без обращения к сохраненному состоянию экземпляра (т.е. выполняет откат к последней сохраненной точке).  
  
     **абандонандсуспенд**  
     Прерывает работу экземпляра в памяти и обновляет приостанавливаемый сохраненный экземпляр.  
  
     **Отмена**  
     Вызывает отмену обработчиков экземпляра, а затем завершает работу экземпляра в памяти, что может удалить его из хранилища экземпляров.  
  
     **terminate**  
     Завершает работу экземпляра в памяти и удаляет его из хранилища экземпляров.  
  
     Дополнительные сведения о <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>см. в разделе [Расширяемость узла службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>См. также

- [Расширяемость узла службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)
