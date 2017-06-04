---
title: "Практическое руководство. Создание базового контракта данных для класса или структуры | Microsoft Docs"
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
helpviewer_keywords: 
  - "контракты данных [WCF], создание для класса или структуры"
  - "класс DataContractAttribute"
  - "DataMemberAttribute"
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Практическое руководство. Создание базового контракта данных для класса или структуры
В этом разделе приведены основные этапы создания контракта данных с использованием класса или структуры.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] контрактах данных и способах их использования см. в разделе [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 Этапы создания базовой службы и клиента [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] см. в разделе [Учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md).  Пример образца работающего приложения, состоящего из базовой службы и клиента, см. в разделе [Базовый контракт данных](../../../../docs/framework/wcf/samples/basic-data-contract.md).  
  
### Создание базового контракта данных для класса или структуры  
  
1.  Объявите, что типы имеют контракт данных, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу.  Обратите внимание, что все открытые типы, включая типы без атрибутов, сериализуемы.  Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных при отсутствии атрибута <xref:System.Runtime.Serialization.DataContractAttribute>.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] см. в разделе [Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
2.  Определите члены \(свойства, поля или события\), сериализуемые путем применения атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> к каждому члену.  Эти члены называются членами данных.  По умолчанию все открытые типы сериализуемы.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] см. в разделе [Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
    > [!NOTE]
    >  Можно применить атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к закрытым полям, в результате чего данные будут предоставлены другим пользователям.  Убедитесь, что член не содержит конфиденциальных данных.  
  
## Пример  
 В следующем примере показано создание контракта данных для типа `Person` путем применения атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> к классу и его членам.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## См. также  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [Учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md)