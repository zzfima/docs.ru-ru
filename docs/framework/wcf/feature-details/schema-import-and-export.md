---
title: "Импорт и экспорт схемы | Microsoft Docs"
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
  - "WCF, импорт и экспорт схемы"
  - "класс XsdDataContractExporter"
  - "класс XsdDataContractImporter"
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Импорт и экспорт схемы
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]включает новый модуль сериализации, <xref:System.Runtime.Serialization.DataContractSerializer>. Объект `DataContractSerializer` осуществляет преобразование объектов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] в формат XML и обратно. Помимо собственно сериализатора [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] включает связанные механизмы импорта и экспорта схемы. *Схемы* является формальный, точное и обрабатываемое компьютером описание формата XML-данных, создаются сериализатором или могут десериализатором. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется язык определения схемы XML (XSD) консорциума W3C (XSD) в качестве представления схемы, которая поддерживает возможность взаимодействия с многочисленными сторонними платформами.  
  
 Компонент импорта схемы <xref:System.Runtime.Serialization.XsdDataContractImporter>принимает документ схемы XSD и создает [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] классы (обычно классы контракта данных) таким образом, чтобы сериализованные формы соответствовали заданной схеме.  
  
 Например, следующий фрагмент схемы:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 создает следующий тип (он немного упрощен для удобства восприятия).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Обратите внимание, что созданный тип соответствует несколько лучших способов контракта данных (в [рекомендации: управление версиями контракта данных](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):  
  
-   Тип реализует <xref:System.Runtime.Serialization.IExtensibleDataObject> интерфейса. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Контракты данных прямой совместимостью](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
-   Данные-члены реализованы в виде открытых свойств, скрывающих закрытые поля.  
  
-   Класс является разделяемым, и его можно дополнять без изменения уже созданного кода.  
  
 <xref:System.Runtime.Serialization.XsdDataContractExporter> позволяет выполнять обратную операцию-принимать типы, сериализуемые с `DataContractSerializer` и создавать документ схемы XSD.  
  
## <a name="fidelity-is-not-guaranteed"></a>Совпадение не гарантируется  
 Нет гарантии, что при выполнении полного цикла преобразования схемы или типа будет обеспечено полное совпадение. (Объект *кругового пути* означает Импорт схемы для создания набора классов и экспорт результата для повторного создания схемы.) Возвращенная схема может не совпадать с исходной. Обратный процесс также не гарантирует полного совпадения результатов. (Выполните экспорт типа для создания схемы и последующий импорт результата. Маловероятно, что будет получен такой же тип.)  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Модель контракта данных поддерживает только ограниченный набор элементов схемы, определенных консорциумом WC3. Если схема не соответствует этому ограниченному набору, во время импорта будет создано исключение. Например, не существует способа преобразовать член с данными контракта данных в атрибут XML. Таким образом, схемы, требующие использования атрибутов XML, не поддерживаются и вызывают появление исключений во время импорта, поскольку в этом случае невозможно создать контракт данных с правильным XML-представлением.  
  
 Например, следующий фрагмент схемы невозможно импортировать с использованием параметров импорта по умолчанию.  
  
 <!-- TODO: review snippet reference [!code[c_SchemaImportExport#9](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  -->  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Если схема не соответствует правилам контракта данных, следует использовать другой механизм сериализации. Например <xref:System.Xml.Serialization.XmlSerializer> использует свой собственный механизм импорта схемы. Кроме того, имеется специальный режим импорта, где список поддерживаемых элементов схемы развертывается. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]в разделе о создании <xref:System.Xml.Serialization.IXmlSerializable> типы в [Импорт схемы для создания классов](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 Класс `XsdDataContractExporter` поддерживает все типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], которые можно сериализовать с помощью класса `DataContractSerializer`. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Типы, поддерживаемые сериализатором контракта данных](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md). Обратите внимание, что схема, созданная с помощью `XsdDataContractExporter` — обычно допустимые данные, `XsdDataContractImporter` можно использовать (если не <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> используется для изменения схемы).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью <xref:System.Runtime.Serialization.XsdDataContractImporter>, в разделе [Импорт схемы для создания классов](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью <xref:System.Runtime.Serialization.XsdDataContractExporter>, в разделе [Экспорт схем из классов](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Runtime.Serialization.XsdDataContractImporter>   
 <xref:System.Runtime.Serialization.XsdDataContractExporter>   
 [Импорт схемы для создания классов](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)   
 [Экспорт схем из классов](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)