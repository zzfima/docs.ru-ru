---
title: "Эквивалентность контрактов данных | Microsoft Docs"
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
  - "контракты данных [WCF], эквивалентность"
ms.assetid: f06f3c7e-c235-4ec1-b200-68142edf1ed1
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Эквивалентность контрактов данных
Чтобы клиент мог успешно отправлять данные определенного типа службе или чтобы служба могла успешно отправлять данные клиенту, отправляемый тип не обязательно должен существовать на принимающей стороне.  Единственное требование заключается в эквивалентности контрактов данных обоих типов.  \(Иногда строгая эквивалентность не требуется, как описано в разделе [Управление версиями контракта данных](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md).\)  
  
 Чтобы контракты данных были эквивалентны, они должны иметь одинаковые пространство имен и имя.  Кроме того, каждый член данных на одной стороне должен иметь эквивалентный член данных на другой стороне.  
  
 Чтобы члены данных были эквивалентны, они должны иметь одинаковое имя.  Кроме того, они должны представлять один и тот же тип данных, т. е. их контракты данных должны быть эквивалентны.  
  
> [!NOTE]
>  Обратите внимание, что в именах контрактов данных и пространствах имен, равно как и в именах членов данных, учитывается регистр.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]б именах контрактов данных и пространствах имен, а также об именах членов данных, см. в разделе [Имена контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-names.md).  
  
 Если два типа существуют на одной и той же стороне \(отправителя или получателя\) и их контракты данных не эквивалентны \(например, имеют разные члены данных\), не следует давать им одно и то же имя и пространство имен.  Это может привести к возникновению исключений.  
  
 Контракты данных для следующих типов эквивалентны:  
  
 [!code-csharp[C_DataContractNames#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#5)]
 [!code-vb[C_DataContractNames#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#5)]  
  
## Эквивалентность порядка членов данных и контрактов данных  
 Использование свойства <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> класса <xref:System.Runtime.Serialization.DataMemberAttribute> может повлиять на эквивалентность контрактов данных.  Чтобы контракты данных были эквивалентны, члены данных в них должны следовать в одинаковом порядке.  По умолчанию они следуют в алфавитном порядке.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Порядок элементов данных](../../../../docs/framework/wcf/feature-details/data-member-order.md).  
  
 Например, следующий код представляет собой эквивалентные контракты данных.  
  
 [!code-csharp[C_DataContractNames#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#6)]
 [!code-vb[C_DataContractNames#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#6)]  
  
 В то же время следующие примеры не являются эквивалентными контрактами данных.  
  
 [!code-csharp[C_DataContractNames#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#7)]
 [!code-vb[C_DataContractNames#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#7)]  
  
## Наследование, интерфейсы и эквивалентность контрактов данных  
 При определении эквивалентности контракт данных, наследующий от других контрактов данных, рассматривается так, как будто это просто контракт данных, включающий все члены данных из базового типа.  Следует помнить, что порядок членов данных должен совпадать, и что члены базового типа должны идти перед членами производного типа.  Кроме того, если, как в следующем примере кода, два члена данных имеют одно и то же значение порядка, эти члены данных располагаются в алфавитном порядке.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Порядок элементов данных](../../../../docs/framework/wcf/feature-details/data-member-order.md).  
  
 В следующем примере контракт данных для типа `Employee` эквивалентен контракту данных для типа `Worker`.  
  
 [!code-csharp[C_DataContractNames#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#8)]
 [!code-vb[C_DataContractNames#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#8)]  
  
 При передаче параметров и возвращаемых значений между клиентом и службой нельзя отправить контракт данных от базового класса, когда принимающая конечная точка ожидает контракт данных от производного класса.  Это соответствует принципам объектно\-ориентированного программирования.  Продолжая предыдущий пример, нельзя отправить объект типа `Person`, если ожидается объект типа `Employee` .  
  
 Можно отправить контракт данных от производного класса, когда ожидается контракт данных от базового класса, однако только при условии, что принимающая конечная точка "знает" производный тип путем использования атрибута <xref:System.Runtime.Serialization.KnownTypeAttribute>.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  В предыдущем примере можно отправить объект типа `Employee`, если ожидается объект типа `Person`, однако только если в принимающем коде присутствует атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute> для включения этого типа в список известных типов.  
  
 Если при передаче параметров и возвращаемых значений между приложениями ожидаемый тип представляет собой интерфейс, это эквивалентно тому, что ожидаемый тип принадлежит к типу <xref:System.Object>.  Поскольку все типы в конечном итоге наследуются от <xref:System.Object>, все контракты данных в конечном итоге наследуются от контракта данных для <xref:System.Object>.  Таким образом, когда ожидается интерфейс, передать можно любой контракт данных.  Для успешной работы с интерфейсами требуются дополнительные действия; дополнительные сведения см. в разделе [Известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## См. также  
 <xref:System.Runtime.Serialization.DataContractAttribute>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>   
 [Порядок элементов данных](../../../../docs/framework/wcf/feature-details/data-member-order.md)   
 [Известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [Имена контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-names.md)