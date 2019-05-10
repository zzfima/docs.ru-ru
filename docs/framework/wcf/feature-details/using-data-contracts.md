---
title: Использование контрактов данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataContractAttribute class
- WCF, data
- data contracts [WCF]
ms.assetid: a3ae7b21-c15c-4c05-abd8-f483bcbf31af
ms.openlocfilehash: 0f33bdc006c6b965ba60257637f3cef182555d7d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637724"
---
# <a name="using-data-contracts"></a>Использование контрактов данных
*Контракт данных* - формальное соглашение между службой и клиентом, абстрактно описывающее данные, обмен которыми происходит. Это значит, что для взаимодействия клиент и служба не обязаны совместно использовать одни и те же типы, достаточно совместно использовать одни и те же контракты данных. Контракт данных для каждого параметра и возвращаемого типа четко определяет, какие данные сериализуются (превращаются в XML) для обмена.  
  
## <a name="data-contract-basics"></a>Основные сведения о контрактах данных  
 Windows Communication Foundation (WCF) использует механизм сериализации, называемый сериализатором контракта данных по умолчанию для сериализации и десериализации данных (преобразования в XML и обратно). Все типы-примитивы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , такие как integer и string, а также некоторые типы, которые обрабатываются как примитивы, такие как <xref:System.DateTime> и <xref:System.Xml.XmlElement>, могут быть сериализованы без дополнительной обработки и считаются типами, которые по умолчанию содержат контракты данных. Многие типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] также содержат контракты данных. Полный список сериализуемых типов см. в разделе [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
 Для сериализации новых созданных сложных типов необходимо определить контракты данных. По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> определяет контракт данных и сериализует все открытые типы. Все открытые свойства чтения/записи и поля типа сериализуются. Можно исключать члены из сериализации с помощью <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>. Также можно явно создавать контракт данных с помощью атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> . Обычно это делается с помощью применения атрибута <xref:System.Runtime.Serialization.DataContractAttribute> к типу. Данный атрибут может быть применен к классам, структурам и перечислениям. После этого необходимо применить атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> к каждому члену типа контракта данных, чтобы указать, что он является *членом данных*, который необходимо сериализовать. Дополнительные сведения см. в разделе [сериализуемых типов](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
### <a name="example"></a>Пример  
 В следующем примере показано явное применение атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> к контракту службы (интерфейсу). В нем показано, что типы-примитивы не требуют контрактов данных, в отличие от сложных типов.  
  
 [!code-csharp[C_DataContract#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#1)]
 [!code-vb[C_DataContract#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#1)]  
  
 В следующем примере показано создание контракта данных для типа `MyTypes.PurchaseOrder` путем применения атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> к классу и его членам.  
  
 [!code-csharp[C_DataContract#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#2)]
 [!code-vb[C_DataContract#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#2)]  
  
### <a name="notes"></a>Примечания  
 Существуют некоторые моменты, которые необходимо учитывать при создании контрактов данных:  
  
- Атрибут <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> учитывается только при использовании в неотмеченных типах. Сюда входят типы, которые не отмечены ни одним из атрибутов <xref:System.Runtime.Serialization.DataContractAttribute>, <xref:System.SerializableAttribute>, <xref:System.Runtime.Serialization.CollectionDataContractAttribute>, <xref:System.Runtime.Serialization.EnumMemberAttribute> или отмечены как сериализуемые любыми другими способами (например, <xref:System.Xml.Serialization.IXmlSerializable>).  
  
- Атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> применим к полям и свойствам.  
  
- Уровни доступности членов (внутренний, закрытый, защищенный или открытый) никак не влияют на контракт данных.  
  
- Атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> игнорируется, если он применен к статическому члену.  
  
- Во время сериализации для членов данных свойств вызывается код property-get, возвращающий значения сериализуемых свойств.  
  
- Во время сериализации вначале создается неинициализированный объект без вызова каких-либо конструкторов типа. Затем десериализуются все члены данных.  
  
- Во время десериализации для членов данных свойств вызывается код property-set, задающий значения сериализуемым свойствам.  
  
- Чтобы контракт данных был допустимым, все его члены данных должны быть сериализуемыми. Полный список сериализуемых типов см. в разделе [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
     Универсальные типы обрабатываются таким же образом, как и неуниверсальные. Для универсальных параметров нет особых требований. Например, рассмотрим следующий тип:  
  
 [!code-csharp[C_DataContract#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#3)]
 [!code-vb[C_DataContract#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#3)]  
  
 Этот тип является сериализуемым независимо от того, используется ли для параметра универсального типа (`T`) сериализуемый тип или нет. Поскольку все члены данных должны быть сериализуемыми, следующий тип является сериализуемым, только если параметр универсального типа также является сериализуемым, как показано в следующем коде.  
  
 [!code-csharp[C_DataContract#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#4)]
 [!code-vb[C_DataContract#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#4)]  
  
 Полный образец кода службы WCF, которая определяет контракт данных, см. в примере [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) .  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md)
- [Имена контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-names.md)
- [Эквивалентность контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)
- [Порядок членов данных](../../../../docs/framework/wcf/feature-details/data-member-order.md)
- [Известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [Контракты данных, совместимые с любыми будущими изменениями](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)
- [Управление версиями контракта данных](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)
- [Обратные вызовы сериализации, независимые от версий](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md)
- [Значения членов данных по умолчанию](../../../../docs/framework/wcf/feature-details/data-member-default-values.md)
- [Типы, поддерживаемые сериализатором контракта данных](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
- [Практическое руководство. Создание базового контракта данных для класса или структуры](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
