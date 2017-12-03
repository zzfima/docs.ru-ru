---
title: "Экспорт схем из классов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, schema import and export
- schemas [WCF], exporting from classes
- schemas [WCF]
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: bb57b962-70c1-45a9-93d5-e721e340a13f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b60b31133a3721611285b5b4caa93d3c34e193f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="exporting-schemas-from-classes"></a>Экспорт схем из классов
Чтобы создать схемы языка определения схемы XML (XSD) из классов, используемых в модели контракта данных, используйте класс <xref:System.Runtime.Serialization.XsdDataContractExporter> . В данном разделе описывается процесс создания схем.  
  
## <a name="the-export-process"></a>Процесс экспорта  
 Процесс экспорта схемы начинается с одного или нескольких типов, что приводит к созданию класса <xref:System.Xml.Schema.XmlSchemaSet> , описывающего XML-проекцию этих типов.  
  
 Класс `XmlSchemaSet` является частью объектной модели схемы (SOM) [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], представляющей набор документов схемы XSD. Чтобы создать документы XSD из класса `XmlSchemaSet`, используйте коллекцию схем из свойства <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> класса `XmlSchemaSet` . Затем сериализуйте каждый объект <xref:System.Xml.Schema.XmlSchema> с помощью сериализатора <xref:System.Xml.Serialization.XmlSerializer>.  
  
#### <a name="to-export-schemas"></a>Экспорт схем  
  
1.  Создайте экземпляр класса <xref:System.Runtime.Serialization.XsdDataContractExporter>.  
  
2.  Необязательно. Передайте объект <xref:System.Xml.Schema.XmlSchemaSet> в конструктор. В этом случае схема, созданная во время экспорта схемы, добавляется в этот экземпляр класса <xref:System.Xml.Schema.XmlSchemaSet> вместо создания нового пустого экземпляра класса <xref:System.Xml.Schema.XmlSchemaSet>.  
  
3.  Необязательно. Вызовите один из методов <xref:System.Runtime.Serialization.XsdDataContractExporter.CanExport%2A> . Этот метод определяет, можно ли экспортировать заданный тип. Этот метод имеет те же перегрузки, что метод `Export` в следующем шаге.  
  
4.  Вызовите один из методов <xref:System.Runtime.Serialization.XsdDataContractExporter.Export%2A> . Существует три перегрузки, получающие <xref:System.Type>и <xref:System.Collections.Generic.List%601> объектов `Type` или <xref:System.Collections.Generic.List%601> объектов <xref:System.Reflection.Assembly> . В последнем случае, экспортируются все типы во всех указанных сборках.  
  
     При нескольких вызовах метода `Export` в один и тот же объект `XmlSchemaSet`добавляется несколько типов. Тип не создается в объекте `XmlSchemaSet` , если он уже имеется в нем. Следовательно, рекомендуется вызывать метод `Export` несколько раз в одном и том же классе `XsdDataContractExporter` , а не создавать несколько экземпляров класса `XsdDataContractExporter` . Это помогает избежать создания повторяющихся типов схем.  
  
    > [!NOTE]
    >  В случае сбоя при экспорте объект `XmlSchemaSet` будет находиться в непредсказуемом состоянии.  
  
5.  Для доступа к объекту <xref:System.Xml.Schema.XmlSchemaSet> используется свойство <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas%2A> .  
  
## <a name="export-options"></a>Параметры экспорта  
 Можно присвоить свойство <xref:System.Runtime.Serialization.XsdDataContractExporter.Options%2A> объекта <xref:System.Runtime.Serialization.XsdDataContractExporter> экземпляру класса <xref:System.Runtime.Serialization.ExportOptions> для управления различными аспектами процесса экспорта. В частности, можно задать следующие параметры.  
  
-   <xref:System.Runtime.Serialization.ExportOptions.KnownTypes%2A>. В этой коллекции `Type` представлены известные типы для экспортируемых типов. ([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Известные типы контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).) Эти известные типы экспортируются при каждом вызове метода `Export` в дополнение к типам, передаваемым в метод `Export`.  
  
-   <xref:System.Runtime.Serialization.ExportOptions.DataContractSurrogate%2A>. С помощью этого свойства можно указать <xref:System.Runtime.Serialization.IDataContractSurrogate> для настройки процесса экспорта. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Суррогаты контракта данных](../../../../docs/framework/wcf/extending/data-contract-surrogates.md). По умолчанию суррогат не используется.  
  
## <a name="helper-methods"></a>Вспомогательные методы  
 Помимо выполнения основной задачи, заключающейся в экспорте схемы, экспортер `XsdDataContractExporter` предлагает несколько полезных вспомогательных методов, предоставляющих сведения о типах. К ним относятся следующие методы.  
  
-   Метод<xref:System.Runtime.Serialization.XsdDataContractExporter.GetRootElementName%2A> . Этот метод принимает `Type` и возвращает имя <xref:System.Xml.XmlQualifiedName> , представляющее имя и пространство имен корневого элемента, которые бы использовались, если бы этот тип был сериализован как корневой объект.  
  
-   Метод<xref:System.Runtime.Serialization.XsdDataContractExporter.GetSchemaTypeName%2A> . Этот метод принимает `Type` и возвращает имя <xref:System.Xml.XmlQualifiedName> , представляющее имя типа схемы XSD, которое бы использовалось, если бы этот тип был экспортирован в схему. В случае типов <xref:System.Xml.Serialization.IXmlSerializable> , представленных как анонимные типы в схеме, этот метод возвращает значение `null`.  
  
-   Метод<xref:System.Runtime.Serialization.XsdDataContractExporter.GetSchemaType%2A> . Этот метод работает только с типами <xref:System.Xml.Serialization.IXmlSerializable> , представленными как анонимные типы в схеме, и возвращает значение `null` для всех других типов. В случае анонимных типов этот метод возвращает тип <xref:System.Xml.Schema.XmlSchemaType> , представляющий данный `Type`.  
  
 Параметры экспорта влияют на все эти методы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.XsdDataContractImporter>  
 <xref:System.Runtime.Serialization.XsdDataContractExporter>  
 [Импорт и Экспорт схемы](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md)  
 [Импорт схемы для создания классов](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)
