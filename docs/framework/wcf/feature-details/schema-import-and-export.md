---
title: Импорт и экспорт схемы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
ms.openlocfilehash: c9bb0d6df362380a37ae3079694ab91e9577741d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="schema-import-and-export"></a>Импорт и экспорт схемы
Windows Communication Foundation (WCF) включает новый модуль сериализации, <xref:System.Runtime.Serialization.DataContractSerializer>. Объект `DataContractSerializer` осуществляет преобразование объектов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] в формат XML и обратно. Помимо собственно сериализатора WCF включает связанные механизмы импорта и схемы экспорта. *Схемы* формальное, точное и обрабатываемое компьютером описание формата XML-данных, которые создаются сериализатором или могут десериализатором. WCF использует язык определения World Wide Web Consortium (W3C) XML-схемы (XSD) в качестве представления схемы, которая поддерживает возможность взаимодействия с многочисленными платформами сторонних разработчиков.  
  
 Компонент импорта схемы <xref:System.Runtime.Serialization.XsdDataContractImporter> принимает документ схемы XSD и создает классы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (обычно это классы контракта данных) таким образом, чтобы сериализованные формы соответствовали заданной схеме.  
  
 Например, следующий фрагмент схемы:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 создает следующий тип (он немного упрощен для удобства восприятия).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Обратите внимание, что созданный тип соответствует несколько лучших способов контракта данных (в [рекомендации: управление версиями контракта данных](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):  
  
-   Тип реализует интерфейс <xref:System.Runtime.Serialization.IExtensibleDataObject>. Дополнительные сведения о создании контрактов данных, обладающих прямой совместимостью, см. в разделе [Контракты данных, совместимые с любыми будущими изменениями](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
-   Данные-члены реализованы в виде открытых свойств, скрывающих закрытые поля.  
  
-   Класс является разделяемым, и его можно дополнять без изменения уже созданного кода.  
  
 Класс <xref:System.Runtime.Serialization.XsdDataContractExporter> позволяет выполнять обратную операцию - принимать типы, сериализуемые с помощью `DataContractSerializer`, и создавать документ схемы XSD.  
  
## <a name="fidelity-is-not-guaranteed"></a>Совпадение не гарантируется  
 Нет гарантии, что при выполнении полного цикла преобразования схемы или типа будет обеспечено полное совпадение. (A *кругового пути* означает Импорт схемы для создания набора классов и экспорт результата для повторного создания схемы.) Возвращенная схема может не совпадать с исходной. Обратный процесс также не гарантирует полного совпадения результатов. (Выполните экспорт типа для создания схемы и последующий импорт результата. Маловероятно, что будет получен такой же тип.)  
  
## <a name="supported-types"></a>Поддерживаемые типы  
 Модель контракта данных поддерживает только ограниченный набор элементов схемы, определенных консорциумом WC3. Если схема не соответствует этому ограниченному набору, во время импорта будет создано исключение. Например, не существует способа преобразовать член с данными контракта данных в атрибут XML. Таким образом, схемы, требующие использования атрибутов XML, не поддерживаются и вызывают появление исключений во время импорта, поскольку в этом случае невозможно создать контракт данных с правильным XML-представлением.  
  
 Например, следующий фрагмент схемы невозможно импортировать с использованием параметров импорта по умолчанию.  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 Дополнительные сведения см. в разделе [Справочник по схеме контрактов данных](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Если схема не соответствует правилам контракта данных, следует использовать другой механизм сериализации. Например, класс <xref:System.Xml.Serialization.XmlSerializer> использует собственный механизм импорта схемы. Кроме того, имеется специальный режим импорта, где список поддерживаемых элементов схемы развертывается. Дополнительные сведения см. в разделе о создании <xref:System.Xml.Serialization.IXmlSerializable> типы в [Импорт схемы для создания классов](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 Класс `XsdDataContractExporter` поддерживает все типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], которые можно сериализовать с помощью класса `DataContractSerializer`. Дополнительные сведения см. в разделе [типы, поддерживаемые сериализатором контракта данных](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md). Обратите внимание, что схема, созданная с помощью класса `XsdDataContractExporter`, обычно содержит допустимые данные, которые могут использоваться классом `XsdDataContractImporter` (если только для изменения схемы не используется класс <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>).  
  
 Дополнительные сведения об использовании <xref:System.Runtime.Serialization.XsdDataContractImporter>, в разделе [Импорт схемы для создания классов](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 Дополнительные сведения об использовании <xref:System.Runtime.Serialization.XsdDataContractExporter>, в разделе [Экспорт схем из классов](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.XsdDataContractImporter>  
 <xref:System.Runtime.Serialization.XsdDataContractExporter>  
 [Импорт схемы для создания классов](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)  
 [Экспорт схем из классов](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)
