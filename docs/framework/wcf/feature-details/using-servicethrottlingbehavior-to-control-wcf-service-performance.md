---
title: "Использование ServiceThrottlingBehavior для управления производительностью службы WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "поведение [WCF], производительность службы"
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Использование ServiceThrottlingBehavior для управления производительностью службы WCF
<xref:System.ServiceModel.Description.ServiceThrottlingBehavior> класс предоставляет свойства, которые можно использовать для ограничения количества экземпляров или сеансов, создаваемых на уровне приложения. С помощью этого поведения можно точно настроить производительность приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Управление экземплярами службы и одновременными вызовами  
 Используйте <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> свойство, чтобы указать максимальное количество сообщений, обрабатываемых <xref:System.ServiceModel.ServiceHost> класс и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> свойство, чтобы указать максимальное число <xref:System.ServiceModel.InstanceContext> объектов в службе.  
  
 Поскольку определение параметров для этих свойств обычно производится после реальных работу при запуске приложения для загрузки параметров для <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> свойства обычно задается в файле конфигурации приложения с помощью [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) элемента.  
  
 В следующем примере кода показано использование <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> класс из файла конфигурации приложения, который задает <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> свойства 1 в качестве упрощенного примера. Фактические условия определяют оптимальные параметры для каждого конкретного приложения.  
  
 <!-- TODO: review snippet reference [!code-csharp[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  -->  
  
 Точное поведение времени выполнения зависит от значения <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> и <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> свойства, которые определяют, сколько сообщений могут обрабатываться в операции одновременно и временем существования службы <xref:System.ServiceModel.InstanceContext> относительно сеансов входящих каналов, соответственно.  
  
 Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, и <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>   
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>