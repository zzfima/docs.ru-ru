---
title: "Практическое руководство. Управление созданием экземпляров служб | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Практическое руководство. Управление созданием экземпляров служб
Установка режима экземпляра службы позволяет определить, когда будет создаваться объект <xref:System.ServiceModel.InstanceContext?displayProperty=fullName> \(и связанный с ним определяемый пользователем объект службы\).  Возможные режимы см. в перечислении <xref:System.ServiceModel.InstanceContextMode>.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] режимах см. в разделе [Настройка и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  Рабочие примеры см. в разделе [Поведение](../../../../docs/framework/wcf/samples/behaviors.md).  
  
### Управление временем существования экземпляра службы с помощью кода  
  
1.  Примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу службы.  
  
2.  Присвойте свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> одно из следующих значений: <xref:System.ServiceModel.InstanceContextMode>, <xref:System.ServiceModel.InstanceContextMode> или <xref:System.ServiceModel.InstanceContextMode>.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## Пример  
 В следующем примере кода свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute> присваивается значение <xref:System.ServiceModel.InstanceContextMode>.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## См. также  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>   
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>   
 <xref:System.ServiceModel.InstanceContextMode>   
 [Service: Behaviors Samples](http://msdn.microsoft.com/ru-ru/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)