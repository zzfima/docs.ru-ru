---
title: "Набор сведений для постсхемной компиляции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 7f1bc7f4-401b-459f-9078-f099cc711fde
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Набор сведений для постсхемной компиляции
В статье [Рекомендации консорциума W3C по схемам XML](http://go.microsoft.com/fwlink/?linkid=45242) рассматривается информационный набор, который должен предоставляться до проверки и после компиляции схемы.  Модель XML SOM просматривает информационные наборы до и после вызова метода <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> объекта <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 Информационный набор до проверки по схеме строится во время изменения схемы.  Информационный набор после компиляции схемы формируется после вызова метода <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> объекта <xref:System.Xml.Schema.XmlSchemaSet> во время компиляции схемы и предоставляется в виде свойств.  
  
 Модель SOM \- это модель объектов, представляющая информационные наборы до и после компиляции схемы и состоящая из классов в пространстве имен <xref:System.Xml.Schema?displayProperty=fullName>.  Все свойства чтения и записи классов в пространстве имен <xref:System.Xml.Schema> принадлежат информационному набору до проверки по схеме, а все свойства «только для чтения» классов в пространстве имен <xref:System.Xml.Schema> принадлежат информационному набору после компиляции схемы.  Исключением из этого правила являются следующие свойства, которые относятся как к информационному набору до проверки по схеме, так и к информационному набору после компиляции схемы.  
  
|Класс|Свойство|  
|-----------|--------------|  
|<xref:System.Xml.Schema.XmlSchemaObject>|<xref:System.Xml.Schema.XmlSchemaObject.Parent%2A>|  
|<xref:System.Xml.Schema.XmlSchema>|<xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A>|  
|<xref:System.Xml.Schema.XmlSchemaExternal>|<xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>|  
|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup.AnyAttribute%2A>|  
|<xref:System.Xml.Schema.XmlSchemaParticle>|<xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A>|  
|<xref:System.Xml.Schema.XmlSchemaComplexType>|<xref:System.Xml.Schema.XmlSchemaComplexType.AnyAttribute%2A>|  
  
 Например, оба класса, <xref:System.Xml.Schema.XmlSchemaElement> и <xref:System.Xml.Schema.XmlSchemaComplexType>, имеют свойства `BlockResolved` и `FinalResolved`.  Эти свойства служат для сохранения значений свойств `Block` и `Final` после компиляции и проверки схемы.  Свойства `BlockResolved` и `FinalResolved` доступны только для чтения и являются частью информационного набора после компиляции схемы.  
  
 В следующем примере показано свойство <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> класса <xref:System.Xml.Schema.XmlSchemaElement>, заданное после проверки схемы.  До проверки свойство содержит ссылку `null`, и свойству <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> присвоено имя данного типа.  После проверки свойство <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> разрешается в допустимый тип, а объект типа становится доступным через свойство <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A>.  
  
 [!code-cpp[PsciSample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/PsciSample/CPP/PsciSample.cpp#1)]
 [!code-csharp[PsciSample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/PsciSample/CS/PsciSample.cs#1)]
 [!code-vb[PsciSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/PsciSample/VB/PsciSample.vb#1)]  
  
## См. также  
 [Модель объектов схемы XML \(SOM\)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)