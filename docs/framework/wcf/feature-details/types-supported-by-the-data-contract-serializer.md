---
title: Типы, поддерживаемые сериализатором контракта данных
ms.date: 03/30/2017
helpviewer_keywords:
- serialization [WCF], supported types
ms.assetid: 7381b200-437a-4506-9556-d77bf1bc3f34
ms.openlocfilehash: f3eedda6c9493688680099f4b07810aebf69ff8a
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249465"
---
# <a name="types-supported-by-the-data-contract-serializer"></a>Типы, поддерживаемые сериализатором контракта данных

Фонд связи Windows (WCF) использует в <xref:System.Runtime.Serialization.DataContractSerializer> качестве своего движка сериализации по умолчанию для преобразования данных в XML и преобразования XML обратно в данные. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> предназначен для сериализации типов *контрактов данных* . Однако поддерживаются и многие другие типы, которые можно рассматривать как неявные контракты данных. Полный список сериализуемых типов приведен ниже.

- Все открытые типы, имеющие конструктор без параметров.

- Типы контрактов данных. К этим типам применен атрибут <xref:System.Runtime.Serialization.DataContractAttribute> . Как правило, создавать новые пользовательские типы, представляющие бизнес-объекты, следует в виде типов контрактов данных. Для получения дополнительной информации [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md) [см.](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)

- Типы коллекций. Эти типы представляют списки данных. Это могут быть обычные массивы типов или типы коллекций, например, <xref:System.Collections.ArrayList> и <xref:System.Collections.Generic.Dictionary%602>. Для настройки сериализации таких типов можно использовать атрибут <xref:System.Runtime.Serialization.CollectionDataContractAttribute> , однако это не является обязательным. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md)

- Типы перечисления. Перечисления, включая перечисления флагов, могут быть сериализованы. Типы перечисления также можно пометить атрибутом <xref:System.Runtime.Serialization.DataContractAttribute> . В этом случае каждый член, участвующий в сериализации, должен быть помечен атрибутом <xref:System.Runtime.Serialization.EnumMemberAttribute> . Все непомеченные члены не сериализуются. Для получения дополнительной [Enumeration Types in Data Contracts](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md)информации см.

- Типы-примитивы .NET Framework. Все следующие типы, встроенные в .NET Framework, могут быть сериализованы и считаются типами-примитивами: <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Boolean>, <xref:System.Char>, <xref:System.Decimal>, <xref:System.Object>и <xref:System.String>.

- Другие типы-примитивы. Следующие типы не являются примитивами в .NET Framework, но обрабатываются как примитивы в сериализованной форме XML: <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>, <xref:System.Xml.XmlQualifiedName>и массив <xref:System.Byte>.

  > [!NOTE]
  > В отличие от других типов-примитивов тип <xref:System.DateTimeOffset> не является по умолчанию известным типом. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)

- Типы, помеченные с помощью атрибута <xref:System.SerializableAttribute> . Многие типы, включенные в библиотеку базовых классов .NET Framework, относятся к этой категории. Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> обеспечивает полную поддержку этой модели программирования сериализации, используемой в удаленном взаимодействии .NET Framework в <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>, включая поддержку интерфейса <xref:System.Runtime.Serialization.ISerializable> .

- Типы, представляющие необработанные XML или типы, представляющие ADO.NET реляционные данные. Типы <xref:System.Xml.XmlElement> и массив элементов <xref:System.Xml.XmlNode> поддерживаются для прямого представления XML. Кроме того, поддерживаются типы, реализующие интерфейс <xref:System.Xml.Serialization.IXmlSerializable> , включая связанный атрибут <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> и типы <xref:System.Xml.Linq.XDocument> и <xref:System.Xml.Linq.XElement> . Тип<xref:System.Data.DataTable> ADO.NET и <xref:System.Data.DataSet> тип (а также типированные классы) <xref:System.Xml.Serialization.IXmlSerializable> реализуют интерфейс и поэтому вписываются в эту категорию. Для получения дополнительной информации [ADO.NET](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md)см.

## <a name="limitations-of-using-certain-types-in-partial-trust-mode"></a>Ограничения по использованию определенных типов в режиме частичного доверия

Ниже приведен список ограничений при использовании некоторых типов в режиме частичного доверия.

- Для сериализации или десериализации типа, реализующего интерфейс <xref:System.Runtime.Serialization.ISerializable> , в коде с частичным доверием с использованием <xref:System.Runtime.Serialization.DataContractSerializer> требуются разрешения <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> и <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> .

- При запуске кода WCF в режиме [частичного](../../../../docs/framework/wcf/feature-details/partial-trust.md) `readonly` доверия не `public` `private`поддерживается сериализация и десериализация полей (как, так и ). Это объясняется тем, что созданный код на промежуточном языке является непроверяемым и поэтому требует повышенного уровня разрешений.

- Оба типа <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Xml.Serialization.XmlSerializer> поддерживаются в среде с частичным доверием. При этом использование <xref:System.Runtime.Serialization.DataContractSerializer> зависит от следующих условий.

  - Все сериализуемые типы `[DataContract]` должны быть открытыми.

  - Все сериализуемые поля и свойства `[DataMember]` в типе `[DataContract]` должны быть открытыми и доступными для чтения и записи. Сериализация и десериализация `readonly` полей не поддерживается при запуске WCF в частично доверенном приложении.

  - Сериализатор `[Serializable]`/`ISerializable]` не поддерживается в среде с частичным доверием.

  - Известные типы должны быть заданы в коде или конфигурации уровня компьютера(`Machine.config`). По соображениям безопасности известные типы нельзя задавать в конфигурации уровня приложения.

- Типы, реализующие интерфейс <xref:System.Runtime.Serialization.IObjectReference> , вызывают исключение в среде с частичным доверием, поскольку метод <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%2A> требует разрешения безопасности `[SecurityPermission(SecurityAction.LinkDemand, Flags=SecurityPermissionFlag.SerializationFormatter)]`.

## <a name="additional-notes-on-serialization"></a>Дополнительные замечания о сериализации

В отношении типов, поддерживаемых в сериализаторе контракта данных, действуют следующие правила.

- Сериализатор контракта данных полностью поддерживает универсальные типы.

- Недействительные типы значений полностью поддерживаются serializer контракта данных.

- Типы интерфейсов обрабатываются либо как объекты <xref:System.Object> , либо, в случае интерфейсов коллекций, как типы коллекций.

- Поддерживаются структуры и классы.

- Модель <xref:System.Runtime.Serialization.DataContractSerializer> программирования не поддерживается <xref:System.Xml.Serialization.XmlSerializer> web-ASP.NET. В частности, не поддерживаются такие атрибуты, как <xref:System.Xml.Serialization.XmlElementAttribute> и <xref:System.Xml.Serialization.XmlAttributeAttribute>. Для поддержки этой модели программирования WCF должен <xref:System.Xml.Serialization.XmlSerializer> быть <xref:System.Runtime.Serialization.DataContractSerializer>переключен на использование вместо .

- Тип <xref:System.DBNull> обрабатывается особым образом. Это одноэлементный тип, и при десериализации десериализатор соблюдает одноэлементное ограничение и указывает все ссылки `DBNull` на одноэлементный экземпляр. Поскольку тип `DBNull` сериализуется, ему требуется разрешение <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> .

## <a name="see-also"></a>См. также

- [Типы XML и ADO.NET в контрактах данных](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md)
- [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md)
- [Типы коллекций в контрактах данных](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md)
- [Типы перечислений в контрактах данных](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md)
