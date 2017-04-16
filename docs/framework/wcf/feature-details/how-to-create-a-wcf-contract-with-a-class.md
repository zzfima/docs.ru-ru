---
title: "Как создавать контракт Windows Communication Foundation с помощью класса | Microsoft Docs"
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
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Как создавать контракт Windows Communication Foundation с помощью класса
Контракты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] рекомендуется создавать с помощью интерфейсов.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как определить контракт службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).Описанный здесь альтернативный способ предполагает создание класса и последующее применение атрибута <xref:System.ServiceModel.ServiceContractAttribute> непосредственно к классу, а атрибута <xref:System.ServiceModel.OperationContractAttribute> к каждому из методов класса, являющихся частью контракта.  
  
> [!WARNING]
>  `[ServiceContract]` и `[ServiceContractAttribute]` выполняют то же самое.То же верно для `[OperationContractAttribute]` и `[OperationContract]`.В каждом случае первое является сокращением для обозначения предыдущего контракта.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] контрактах службы см. в разделе [Создание контрактов служб](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### Создание контракта Windows Communication Foundation с помощью класса  
  
1.  Создайте новый класс с использованием языка [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C\# или другого языка среды CLR.  
  
2.  Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к созданному классу.  
  
3.  Создайте методы класса.  
  
4.  Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который требуется предоставить в рамках открытого контракта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Пример  
 В следующем примере кода показан класс, определяющий контракт службы.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос\-ответ».[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об этом шаблоне обмена сообщениями см. в разделе [Как создать контракт типа «запрос\-ответ»](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута.Дополнительные примеры см. в разделах [Как создать односторонний контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [Как создавать дуплексный контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## См. также  
 <xref:System.ServiceModel.ServiceContractAttribute>   
 <xref:System.ServiceModel.OperationContractAttribute>