---
title: "Значения элементов данных по умолчанию | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элементы данных [WCF]"
  - "элементы данных [WCF], значения по умолчанию"
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Значения элементов данных по умолчанию
В платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] у типов имеется концепция *значений по умолчанию*.Например, любой ссылочный тип имеет значение по умолчанию `null`, а значением по умолчанию для целого типа является ноль.Иногда требуется исключить член данных из сериализованных данных, если для него задано значение по умолчанию.Так как этот член имеет значение по умолчанию, нет необходимости сериализовывать фактическое значение; это повышает производительность.  
  
 Чтобы исключить член из сериализованных данных, задайте для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> атрибута <xref:System.Runtime.Serialization.DataMemberAttribute> значение `false` \(по умолчанию задано значение `true`\).  
  
> [!NOTE]
>  Присваивать значение `false` свойству <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> следует только при конкретной необходимости, например для обеспечения взаимодействия или для уменьшения объема данных.  
  
## Пример  
 В следующем коде у нескольких членов для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> задано значение `false`.  
  
 [!code-csharp[DataMemberAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datamemberattribute/cs/overview.cs#4)]
 [!code-vb[DataMemberAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datamemberattribute/vb/overview.vb#4)]  
  
 При сериализации экземпляра этого класса получается следующее: `employeeName` и `employeeID` сериализуются.Значение "null" для `employeeName` и нулевое значение для `employeeID` в явном виде указаны в сериализованных данных.Однако члены `position`, `salary` и `bonus` не сериализуются.Наконец, член `targetSalary` сериализуется как обычно, хотя для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> задано значение `false`, так как 57800 не соответствует принятому в платформе .NET значению по умолчанию для целого числа \(а именно, ноль\).  
  
### Представление XML  
 При сериализации предыдущего примера в XML представление аналогично приведенному ниже.  
  
```  
<Employee>  
   <employeeName xsi:nil="true" />  
   <employeeID>0</employeeID>  
<targetSalary>57800</targetSalary>  
</Employee>  
```  
  
 Атрибут `xsi:nil` является специальным атрибутом в пространстве имен экземпляров схемы XML интернет\-консорциума \(W3C\), который обеспечивает совместимый способ явного указания значения "null".Обратите внимание, что в XML полностью отсутствует информация о членах данных со сведениями о должности, окладе и бонусах.Получатель может интерпретировать их как значения `null`, ноль и `null` соответственно.Не гарантируется, что десериализатор независимого разработчика выполнит правильную интерпретацию, поэтому не рекомендуется использовать такую схему.Класс <xref:System.Runtime.Serialization.DataContractSerializer> всегда выбирает правильную интерпретацию для отсутствующих значений.  
  
### Взаимодействие со свойством IsRequired  
 Как указано в разделе [Управление версиями контракта данных](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md), атрибут <xref:System.Runtime.Serialization.DataMemberAttribute> обладает свойством <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> \(значение по умолчанию — `false`\).Это свойство указывает, должен ли определенный член данных присутствовать в сериализованных данных при десериализации.Если для свойства `IsRequired` задано значение `true` \(означающее, что значение должно присутствовать\), а для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> задано значение `false` \(указывающее, что если значение равно значению по умолчанию, то оно может отсутствовать\), сериализация значений по умолчанию для этого члена данных невозможна, так как результат будет противоречивым.Если для такого члена данных задано значение по умолчанию \(обычно `null` или ноль\) и производится попытка сериализации, возникает исключение <xref:System.Runtime.Serialization.SerializationException>.  
  
### Представление схемы  
 Подробно представление членов данных схемы языка описания схемы XML \(XSD\) в случае, если для свойства `EmitDefaultValue` задано значение `false`, рассматриваются в разделе [Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).Тем не менее ниже приводятся краткие общие сведения:  
  
-   Если для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> задано значение `false`, оно представляется в схеме как заметка, специфичная для [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Не существует совместимого способа представления этой информации.В частности, атрибут "default" в схеме не используется для этой цели, на атрибут `minOccurs` влияет только параметр <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>, а на атрибут `nillable` влияет только тип члена данных.  
  
-   Фактическое значение по умолчанию, которое требуется использовать, в этой схеме отсутствует.Правильная интерпретация отсутствующего элемента зависит только от принимающей конечной точки.  
  
 При импорте схемы для свойства <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> автоматически устанавливается значение `false`, если обнаруживается ранее упомянутая заметка, специфичная для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Кроме того, значение `false` устанавливается для ссылочных типов, у которых для свойства `nillable` задано значение `false`, чтобы обеспечить поддержку специфичных сценариев взаимодействия, часто встречающихся при использовании веб\-служб [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
## См. также  
 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>