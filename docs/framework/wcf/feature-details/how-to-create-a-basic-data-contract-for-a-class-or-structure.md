---
title: "Практическое руководство. Создание базового контракта данных для класса или структуры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e530cfa5cd5716e937318bf8fc458d372202ffeb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a>Практическое руководство. Создание базового контракта данных для класса или структуры
В этом разделе приведены основные этапы создания контракта данных с использованием класса или структуры. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]контракты данных и они используются, в разделе [использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
 Учебник, поможет выполнить этапы создания базового [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] службы и клиента см. в разделе [учебник по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md). Рабочий пример приложения, состоящий из базовой службы и клиента см. в разделе [базовый контракт данных](../../../../docs/framework/wcf/samples/basic-data-contract.md).  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a>Создание базового контракта данных для класса или структуры  
  
1.  Объявите, что типы имеют контракт данных, применив атрибут <xref:System.Runtime.Serialization.DataContractAttribute> к классу. Обратите внимание, что все открытые типы, включая типы без атрибутов, сериализуемы. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных при отсутствии атрибута <xref:System.Runtime.Serialization.DataContractAttribute>. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
2.  Определите члены (свойства, поля или события), сериализуемые путем применения атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> к каждому члену. Эти члены называются членами данных. По умолчанию все открытые типы сериализуемы. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
    > [!NOTE]
    >  Можно применить атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к закрытым полям, в результате чего данные будут предоставлены другим пользователям. Убедитесь, что член не содержит конфиденциальных данных.  
  
## <a name="example"></a>Пример  
 В следующем примере показано создание контракта данных для типа `Person` путем применения атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> к классу и его членам.  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Руководство по началу работы](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md)
