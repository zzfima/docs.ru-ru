---
title: "Сериализуемые типы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c8539a-6a79-4413-b294-896f0957b2cd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e368472db3bdca73661586821106174e13d4d24
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="serializable-types"></a>Сериализуемые типы
По умолчанию <xref:System.Runtime.Serialization.DataContractSerializer> сериализует все открытые типы. Все открытые свойства чтения/записи и поля типа сериализуются.  
  
 Изменить предусмотренное по умолчанию поведение можно, применив к типам и членам атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>. Этим удобно пользоваться в ситуациях, когда разработчик не имеет возможности управлять типами и изменять их для добавления атрибутов. <xref:System.Runtime.Serialization.DataContractSerializer> распознает такие "неотмеченные" типы.  
  
## <a name="serialization-defaults"></a>Параметры сериализации по умолчанию  
 Для явного управления сериализацией или настройки сериализации типов и членов можно применять атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>. Эти атрибуты также можно применять к закрытым полям. В то же время даже типы, не отмеченные этими атрибутами, сериализуются и десериализуются. Действуют следующие правила и исключения.  
  
-   <xref:System.Runtime.Serialization.DataContractSerializer> выводит контракт данных из типов без атрибутов, используя свойства по умолчанию только что созданных типов.  
  
-   Все открытые поля и свойства с открытыми методами `get` и `set` сериализуются, за исключением членов, к которым применен атрибут <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>.  
  
-   Семантика сериализации аналогична семантике <xref:System.Xml.Serialization.XmlSerializer>.  
  
-   В неотмеченных типах сериализуются только открытые типы с не имеющими параметров конструкторами. Исключением из этого правила является объект <xref:System.Runtime.Serialization.ExtensionDataObject>, используемый с интерфейсом <xref:System.Runtime.Serialization.IExtensibleDataObject>.  
  
-   Доступные только для чтения поля, свойства без метода `get` или `set` и свойства с внутренними или закрытыми методами `set` или `get` не сериализуются. Такие свойства игнорируются без вызова исключения, кроме случаев с доступными только для возвращения коллекциями.  
  
-   Атрибуты <xref:System.Xml.Serialization.XmlSerializer> (такие как `XmlElement`, `XmlAttribute`, `XmlIgnore`, `XmlInclude` и т. д.) игнорируются.  
  
-   Если не применить к типу атрибут <xref:System.Runtime.Serialization.DataContractAttribute>, все члены в этом типе, к которым применен атрибут <xref:System.Runtime.Serialization.DataMemberAttribute>, игнорируются сериализатором.  
  
-   Свойство <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A> поддерживается в типах, не отмеченных атрибутом <xref:System.Runtime.Serialization.DataContractAttribute>. Это подразумевает поддержку атрибута <xref:System.Runtime.Serialization.KnownTypeAttribute> на неотмеченных типах.  
  
-   Чтобы исключить из процесса сериализации открытые члены, свойства или поля, применяйте к таким членам атрибут <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>.  
  
## <a name="inheritance"></a>Наследование  
 Неотмеченные типы (типы без атрибута <xref:System.Runtime.Serialization.DataContractAttribute>) могут наследоваться от типов, имеющих этот атрибут. В то же время обратное невозможно: типы с атрибутом от неотмеченных типов наследоваться не могут. Это правило применяется главным образом для обеспечения обратной совместимости с кодом, написанным в более ранних версиях [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [Типы, поддерживаемые сериализатором контракта данных](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
