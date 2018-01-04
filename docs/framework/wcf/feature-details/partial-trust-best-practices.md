---
title: "Рекомендации по частичному доверию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 817f7aeeb7adece1c375bb8b0cc455a17fb54185
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="partial-trust-best-practices"></a>Рекомендации по частичному доверию
В этом разделе описываются рекомендации по использованию [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в среде с частичным доверием.  
  
## <a name="serialization"></a>Сериализация  
 При использовании <xref:System.Runtime.Serialization.DataContractSerializer> в частично доверенном приложении следуйте указанным ниже рекомендациям.  
  
-   Все сериализуемые типы должны быть явно отмечены атрибутом `[DataContract]`. В среде с частичным доверием следующие методы не поддерживаются:  
  
-   маркирование сериализуемых классов атрибутом <xref:System.SerializableAttribute>;  
  
-   реализация интерфейса <xref:System.Runtime.Serialization.ISerializable>, чтобы класс мог управлять своим процессом сериализации.  
  
### <a name="using-datacontractserializer"></a>Использование DataContractSerializer  
  
-   Все типы, отмеченные атрибутом `[DataContract]`, должны быть открытыми. Сериализация неоткрытых типов в среде с частичным доверием невозможна.  
  
-   Все члены `[DataContract]` в сериализуемом типе `[DataContract]` должны быть открытыми. Сериализация типа с неоткрытым членом `[DataMember]` в среде с частичным доверием невозможна.  
  
-   Методы, обрабатывающие события сериализации (например, `OnSerializing`, `OnSerialized`, `OnDeserializing` и `OnDeserialized`) должны быть объявлены как открытые. Однако поддерживаются явные и неявные реализации <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29>.  
  
-   Типы `[DataContract]`, реализованные в сборках, отмеченных атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, не должны выполнять в конструкторе типа действия, связанные с безопасностью, так как <xref:System.Runtime.Serialization.DataContractSerializer> не вызывает конструктор вновь созданного объекта во время десериализации. В частности, для типов `[DataContract]` следует избегать использования указанных ниже общих методов обеспечения безопасности:  
  
-   попытка ограничить доступ с частичным доверием, делая конструктор типа внутренним или закрытым;  
  
-   ограничение доступа к типу путем добавления `[LinkDemand]` в конструктор типа;  
  
-   предположение об успешном прохождении любых принудительно выполняемых конструктором проверок правильности в случае успешного создания объекта.  
  
### <a name="using-ixmlserializable"></a>Использование IXmlSerializable  
 Ниже приведены рекомендации для типов, которые реализуют интерфейс <xref:System.Xml.Serialization.IXmlSerializable> и сериализуются с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
-   Реализации статического метода <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> должны быть `public`.  
  
-   Методы экземпляров, которые реализуют интерфейс <xref:System.Xml.Serialization.IXmlSerializable>, должны быть `public`.  
  
## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a>Использование WCF из кода полностью доверенной платформы, который разрешает вызовы от частично доверенных вызывающих  
 В модели безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с частичным уровнем доверия предполагается, что любой вызов открытого метода или свойства [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] происходит в контексте управления доступом для кода (CAS) ведущего приложения. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также предполагается, что существует только один контекст безопасности приложения для каждого домена <xref:System.AppDomain> и что этот контекст задается во время создания домена <xref:System.AppDomain> доверенным узлом (например, вызовом метода <xref:System.AppDomain.CreateDomain%2A> или диспетчером приложения ASP.NET).  
  
 Эта модель безопасности применяется для написанных пользователем приложений, которые не могут утвердить дополнительные разрешения на управление доступом для кода. Примером такого приложения является пользовательский код, выполняющийся в приложении ASP.NET со средним уровнем доверия. Однако в коде полностью доверенной платформы (например, в сторонней сборке, установленной в глобальном кэше сборок и принимающей вызовы от частично доверенного кода) должны быть приняты меры предосторожности в отношении обращения к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] от имени частично доверенного приложения во избежание ввода уязвимых с точки зрения безопасности мест на уровне приложения.  
  
 В коде с полным доверием следует избегать изменения набора разрешений текущего потока на управление доступом для кода (путем вызова <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> или <xref:System.Security.PermissionSet.Deny%2A>) до вызова интерфейсов API [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] от имени частично доверенного кода. Утверждение, отклонение или создание контекста разрешений потока, который не зависит от контекста безопасности уровня приложения, может привести к непредвиденному поведению. В зависимости от приложения такое поведение может стать причиной появления уязвимых с точки зрения безопасности мест на уровне приложения.  
  
 Код, который обращается в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], используя контекст разрешений потока, должен быть подготовлен к обработке указанных ниже ситуаций, которые могут возникать.  
  
-   Контекст безопасности потока может не поддерживаться в ходе выполнения операции, что приводит к потенциальным исключениям, связанным с безопасностью.  
  
-   Внутренний код [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а также любые предусмотренные пользователем обратные вызовы могут выполняться в контексте безопасности, отличном от контекста, в котором был первоначально инициирован вызов. К таким контекстам относятся следующие.  
  
    -   Контекст разрешений приложения.  
  
    -   Любой контекст разрешений потока, созданный ранее другими пользовательскими потоками, используемыми для обращения в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в течение времени существования работающего в данный момент домена <xref:System.AppDomain>.  
  
 Система [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] гарантирует невозможность получения частично доверенным кодом разрешений с полным доверием, если такие разрешения не утверждены полностью доверенным компонентом до обращения к открытым интерфейсам API [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Однако она не гарантирует, что результаты утверждения полного доверия изолируются для конкретного потока, операции или действия пользователя.  
  
 Рекомендуется избегать создания контекста разрешений потока посредством вызова <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> или <xref:System.Security.PermissionSet.Deny%2A>. Вместо этого предоставьте привилегию самому приложению или отклоните ее, чтобы вызывать <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A> или <xref:System.Security.PermissionSet.PermitOnly%2A> не требовалось.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Xml.Serialization.IXmlSerializable>
