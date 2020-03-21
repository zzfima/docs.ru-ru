---
title: Порядок членов данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 2a5d7430953bdc31644e92b9207cd2865209cce5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185201"
---
# <a name="data-member-order"></a>Порядок членов данных
В некоторых приложениях полезно знать порядок передачи или предполагаемого приема данных от различных элементов данных (например, порядок, в котором данные появляются в сериализованной форме XML). Иногда может потребоваться изменить этот порядок. В этом разделе рассматриваются правила упорядочивания.  
  
## <a name="basic-rules"></a>Основные правила  
 Ниже перечислены основные правила упорядочивания данных.  
  
- Если тип контракта данных является частью иерархии наследования, элементы данных базовых типов всегда идут первыми.  
  
- Затем следуют (в алфавитном порядке) элементы данных текущего типа, для которых не задано свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
- Затем следуют любые элементы данных, для которых задано свойство <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute>. Они упорядочиваются сначала по значению свойства `Order` и затем по алфавиту, если существует несколько элементов определенного значения `Order`. Значения свойства "Order" могут быть пропущены.  
  
 Алфавитный порядок устанавливается посредством вызова метода <xref:System.String.CompareOrdinal%2A>.  
  
## <a name="examples"></a>Примеры  
 Рассмотрим следующий код.  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 Создаваемый XML-код подобен приведенному ниже.  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>
</DerivedType>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Data Contract Equivalence](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)
- [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
