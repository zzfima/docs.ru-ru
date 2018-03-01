---
title: "Типы, поддерживаемые сериализатором контракта данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- serialization [WCF], supported types
ms.assetid: 7381b200-437a-4506-9556-d77bf1bc3f34
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 98eb46e0f31995efe7db177d90691a9f59288590
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="types-supported-by-the-data-contract-serializer"></a>Типы, поддерживаемые сериализатором контракта данных
В[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в качестве модуля сериализации по умолчанию для преобразования данных в формат XML и обратно используется <xref:System.Runtime.Serialization.DataContractSerializer> . Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> предназначен для сериализации типов *контрактов данных* . Однако поддерживаются и многие другие типы, которые можно рассматривать как неявные контракты данных. Полный список сериализуемых типов приведен ниже.  
  
-   Все открытые типы, имеющие конструктор без параметров.  
  
-   Типы контрактов данных. К этим типам применен атрибут <xref:System.Runtime.Serialization.DataContractAttribute> . Как правило, создавать новые пользовательские типы, представляющие бизнес-объекты, следует в виде типов контрактов данных. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md) и [сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
-   Типы коллекций. Эти типы представляют списки данных. Это могут быть обычные массивы типов или типы коллекций, например, <xref:System.Collections.ArrayList> и <xref:System.Collections.Generic.Dictionary%602>. Для настройки сериализации таких типов можно использовать атрибут <xref:System.Runtime.Serialization.CollectionDataContractAttribute> , однако это не является обязательным. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Типы коллекций в контрактах данных](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).  
  
-   Типы перечисления. Перечисления, включая перечисления флагов, могут быть сериализованы. Типы перечисления также можно пометить атрибутом <xref:System.Runtime.Serialization.DataContractAttribute> . В этом случае каждый член, участвующий в сериализации, должен быть помечен атрибутом <xref:System.Runtime.Serialization.EnumMemberAttribute> . Все непомеченные члены не сериализуются. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Типы перечислений в контрактах данных](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).  
  
-   Типы-примитивы .NET Framework. Все следующие типы, встроенные в .NET Framework, могут быть сериализованы и считаются типами-примитивами: <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Boolean>, <xref:System.Char>, <xref:System.Decimal>, <xref:System.Object>и <xref:System.String>.  
  
-   Другие типы-примитивы. Следующие типы не являются примитивами в .NET Framework, но обрабатываются как примитивы в сериализованной форме XML: <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>, <xref:System.Xml.XmlQualifiedName>и массив <xref:System.Byte>.  
  
    > [!NOTE]
    >  В отличие от других типов-примитивов тип <xref:System.DateTimeOffset> не является по умолчанию известным типом. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)).  
  
-   Типы, помеченные с помощью атрибута <xref:System.SerializableAttribute> . В эту категорию попадают многие типы из библиотеки базовых классов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> обеспечивает полную поддержку этой модели программирования сериализации, используемой в удаленном взаимодействии .NET Framework в <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>и <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>, включая поддержку интерфейса <xref:System.Runtime.Serialization.ISerializable> .  
  
-   Типы, представляющие исходный XML, и типы, представляющие реляционные данные [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] . Типы <xref:System.Xml.XmlElement> и массив элементов <xref:System.Xml.XmlNode> поддерживаются для прямого представления XML. Кроме того, поддерживаются типы, реализующие интерфейс <xref:System.Xml.Serialization.IXmlSerializable> , включая связанный атрибут <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> и типы <xref:System.Xml.Linq.XDocument> и <xref:System.Xml.Linq.XElement> . Сериализатор [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]<xref:System.Data.DataTable> и <xref:System.Data.DataSet> (а также его наследуемые типизированные классы) реализуют интерфейс <xref:System.Xml.Serialization.IXmlSerializable> и поэтому тоже попадают в эту категорию. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Типы XML и ADO.NET в контрактах данных](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md).  
  
## <a name="limitations-of-using-certain-types-in-partial-trust-mode"></a>Ограничения по использованию определенных типов в режиме частичного доверия  
 Ниже приведен список ограничений при использовании некоторых типов в режиме частичного доверия.  
  
-   Для сериализации или десериализации типа, реализующего интерфейс <xref:System.Runtime.Serialization.ISerializable> , в коде с частичным доверием с использованием <xref:System.Runtime.Serialization.DataContractSerializer> требуются разрешения <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> и <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> .  
  
-   При выполнении кода [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в режиме [Partial Trust](../../../../docs/framework/wcf/feature-details/partial-trust.md) сериализация и десериализация полей `readonly` ( `public` и `private`) не поддерживается. Это объясняется тем, что созданный код на промежуточном языке является непроверяемым и поэтому требует повышенного уровня разрешений.  
  
-   Оба типа <xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Xml.Serialization.XmlSerializer> поддерживаются в среде с частичным доверием. При этом использование <xref:System.Runtime.Serialization.DataContractSerializer> зависит от следующих условий.  
  
    -   Все сериализуемые типы `[DataContract]` должны быть открытыми.  
  
    -   Все сериализуемые поля и свойства `[DataMember]` в типе `[DataContract]` должны быть открытыми и доступными для чтения и записи. Сериализация и десериализация полей `readonly` не поддерживается при выполнении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в приложении с частичным доверием.  
  
    -   Сериализатор `[Serializable]`/`ISerializable]` не поддерживается в среде с частичным доверием.  
  
    -   Известные типы должны быть заданы в коде или конфигурации уровня компьютера(`Machine.config`). По соображениям безопасности известные типы нельзя задавать в конфигурации уровня приложения.  
  
-   Типы, реализующие интерфейс <xref:System.Runtime.Serialization.IObjectReference> , вызывают исключение в среде с частичным доверием, поскольку метод <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%2A> требует разрешения безопасности `[SecurityPermission(SecurityAction.LinkDemand, Flags=SecurityPermissionFlag.SerializationFormatter)]`.  
  
## <a name="additional-notes-on-serialization"></a>Дополнительные замечания о сериализации  
 В отношении типов, поддерживаемых в сериализаторе контракта данных, действуют следующие правила.  
  
-   Сериализатор контракта данных полностью поддерживает универсальные типы.  
  
-   Сериализатор контракта данных полностью поддерживает типы, допускающие значение null.  
  
-   Типы интерфейсов обрабатываются либо как объекты <xref:System.Object> , либо, в случае интерфейсов коллекций, как типы коллекций.  
  
-   Поддерживаются структуры и классы.  
  
-   Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> не поддерживает модель программирования, используемую в <xref:System.Xml.Serialization.XmlSerializer> и веб-службах [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . В частности, не поддерживаются такие атрибуты, как <xref:System.Xml.Serialization.XmlElementAttribute> и <xref:System.Xml.Serialization.XmlAttributeAttribute>. Чтобы обеспечить поддержку этой модели программирования, необходимо переключить [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для использования <xref:System.Xml.Serialization.XmlSerializer> вместо <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
-   Тип <xref:System.DBNull> обрабатывается особым образом. Это одноэлементный тип, и при десериализации десериализатор соблюдает одноэлементное ограничение и указывает все ссылки `DBNull` на одноэлементный экземпляр. Поскольку тип `DBNull` сериализуется, ему требуется разрешение <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> .  
  
## <a name="see-also"></a>См. также  
 [Типы XML и ADO.NET в контрактах данных](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md)  
 [Использование контрактов данных](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md)  
 [Типы коллекций в контрактах данных](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md)  
 [Типы перечислений в контрактах данных](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md)
