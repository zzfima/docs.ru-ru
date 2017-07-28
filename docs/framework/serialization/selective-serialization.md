---
title: "Выборочная сериализация | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "двоичная сериализация, выборочная сериализация"
  - "сериализация, выборочная сериализация"
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Выборочная сериализация
Класс часто содержит поля, которые не должны быть сериализованы.Например, рассмотрим класс, содержащий идентификатор потока в переменной\-члене.При десериализации класса поток, в котором хранился идентификатор во время сериализации класса, может уже не использоваться, поэтому сериализация такого значения не имеет смысла.Предотвратить сериализацию переменных\-членов можно, маркировав их атрибутом [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic) следующим образом.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```  
  
 Для объекта, содержащего важные для обеспечения безопасности данные, следует, если это возможно, запретить сериализацию.Если же для данного объекта сериализация необходима, примените к соответствующим полям с важной информацией атрибут **NonSerialized**.Учтите, если не исключить эти поля из сериализации, хранимые в них данные будут предоставлены любому коду с разрешением сериализации.Дополнительные сведения о написании безопасного кода сериализации см. в разделе [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md).  
  
## См. также  
 [Двоичная сериализация](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/ru-ru/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML\- и SOAP\-сериализация](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)