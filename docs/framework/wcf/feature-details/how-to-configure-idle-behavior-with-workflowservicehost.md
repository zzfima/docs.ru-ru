---
title: Практическое руководство. Как настроить неактивное поведение с помощью WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
ms.openlocfilehash: d3fc95e7e92d3fc7c149790d4af00a464ab427f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164025"
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a>Практическое руководство. Как настроить неактивное поведение с помощью WorkflowServiceHost
Рабочие процессы переходят в режим бездействия, когда обнаруживают закладку, выполнение которой должно быть возобновлено по внешнему сигналу, например когда экземпляр рабочего процесса ожидает доставки сообщения с помощью действия <xref:System.ServiceModel.Activities.Receive> . <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> Это поведение, которое позволяет указать время между переходом экземпляра службы в состояние бездействия и сохранением или выгрузкой экземпляра. Содержит два свойства, которые позволяют задавать значения для этих периодов времени. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> Указывает интервал времени между переходом экземпляра службы рабочего процесса в состояние бездействия и сохранением экземпляра службы рабочего процесса. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> Указывает период времени между когда экземпляру службы рабочего процесса переходит в состояние бездействия и при выгрузке экземпляра службы рабочего процесса, где выгрузка означает сохранение экземпляра в хранилище экземпляров и удаление его из памяти. В этом разделе описана настройка <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> в файле конфигурации.  
  
### <a name="to-configure-workflowidlebehavior"></a>Настройка WorkflowIdleBehavior  
  
1.  Добавьте <`workflowIdle`> элемента <`behavior`> элемента <`serviceBehaviors`> элемента, как показано в следующем примере.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     Атрибут `timeToUnload` определяет период времени между переходом экземпляра службы рабочего процесса в состояние бездействия и выгрузкой службы рабочего процесса. Атрибут `timeToPersist` определяет период времени между переходом экземпляра службы рабочего процесса в состояние бездействия и сохранением экземпляра службы рабочего процесса. Значение `timeToUnload` по умолчанию составляет 1 минуту. По умолчанию для объекта `timeToPersist` установлено значение <xref:System.TimeSpan.MaxValue>. Если ожидающие экземпляры нужно оставить в памяти, но сохранить для надежности, задайте значения так, чтобы выполнялось неравенство `timeToPersist` < `timeToUnload`. Если требуется, чтобы ожидающие экземпляры не выгружались, задайте параметру `timeToUnload` значение <xref:System.TimeSpan.MaxValue>. Дополнительные сведения о <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, см. в разделе [расширяемость узла службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
  
    > [!NOTE]
    >  В предыдущем образце конфигурации используется упрощенная конфигурация. Дополнительные сведения см. в разделе [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
### <a name="to-change-idle-behavior-in-code"></a>Изменение поведения во время ожидания в коде  
  
-   В следующем примере программным способом изменяется время ожидания перед сохранением и выгрузкой.  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Расширяемость узла службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md)
- [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)
