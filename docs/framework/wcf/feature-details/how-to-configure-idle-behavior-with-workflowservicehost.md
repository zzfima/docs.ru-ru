---
title: Как настроить неактивное поведение с помощью WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
ms.openlocfilehash: 67be47f97e57792e2f1e14505d3cd121729db33b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185085"
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a>Как настроить неактивное поведение с помощью WorkflowServiceHost
Рабочие процессы переходят в режим бездействия, когда обнаруживают закладку, выполнение которой должно быть возобновлено по внешнему сигналу, например когда экземпляр рабочего процесса ожидает доставки сообщения с помощью действия <xref:System.ServiceModel.Activities.Receive> . Поведение<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> позволяет задать время между переходом экземпляра службы в неактивное состояние и его сохранением или выгрузкой. Содержит два свойства, которые позволяют задавать значения для этих периодов времени. Атрибут<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> определяет период времени между переходом экземпляра службы Workflow Service в состояние бездействия и сохранением экземпляра службы Workflow Service. Свойство<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> определяет период времени между переходом экземпляра службы Workflow Service в состояние бездействия и моментом выгрузки экземпляра рабочего процесса, где выгрузка означает сохранение экземпляра в хранилище экземпляров с удалением из памяти. В этом разделе описана настройка <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> в файле конфигурации.  
  
### <a name="to-configure-workflowidlebehavior"></a>Настройка WorkflowIdleBehavior  
  
1. Добавьте `workflowIdle` элемент> <`behavior` в элемент `serviceBehaviors` <> элемент в элемент е<>, как показано в следующем примере.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     Атрибут `timeToUnload` определяет период времени между переходом экземпляра службы рабочего процесса в состояние бездействия и выгрузкой службы рабочего процесса. Атрибут `timeToPersist` определяет период времени между переходом экземпляра службы рабочего процесса в состояние бездействия и сохранением экземпляра службы рабочего процесса. Значение `timeToUnload` по умолчанию составляет 1 минуту. По умолчанию для объекта `timeToPersist` установлено значение <xref:System.TimeSpan.MaxValue>. Если ожидающие экземпляры нужно оставить в памяти, но сохранить для надежности, задайте значения так, чтобы выполнялось неравенство `timeToPersist` < `timeToUnload`. Если требуется, чтобы ожидающие экземпляры не выгружались, задайте параметру `timeToUnload` значение <xref:System.TimeSpan.MaxValue>. Для получения <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>дополнительной информации о, см. [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
  
    > [!NOTE]
    > В предыдущем образце конфигурации используется упрощенная конфигурация. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/simplified-configuration.md)  
  
### <a name="to-change-idle-behavior-in-code"></a>Изменение поведения во время ожидания в коде  
  
- В следующем примере программным способом изменяется время ожидания перед сохранением и выгрузкой.  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md)
- [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)
