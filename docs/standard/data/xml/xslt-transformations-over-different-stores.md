---
title: "XSLT-преобразования над различными хранилищами"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 369850e9-004a-45d2-b5c3-5060d9135adb
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b909b754c1d0d3007e06cd04376413d02cbc2f76
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-transformations-over-different-stores"></a>XSLT-преобразования над различными хранилищами
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в версии [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] устарел. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. В разделе [использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) для получения дополнительной информации.  
  
 ADO.NET и XML-классы платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] предоставляют унифицированную модель программирования для доступа к данным. Данные представляются как XML-данные, то есть в виде текста, разделенного тегами, и как реляционные данные, то есть в виде таблиц, состоящих из строк и столбцов. XML платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] считывают XML-данные из любого потока данных в деревья узлов модели DOM, откуда к данным можно получить доступ программным путем, тогда как ADO.NET предоставляет средства доступа и управления реляционными данными внутри объекта <xref:System.Data.DataSet>.  
  
 Модель XML DOM предоставляет доступ к данным в XML-документах и дополнительные классы для чтения, записи и навигации в XML-документах. Эти классы поддерживаются в пространстве имен <xref:System.Xml>, которое также унифицирует XML DOM со службами доступа к данным, предоставляемым ADO.NET. <xref:System.Xml.XmlDataDocument> предоставляет реляционный доступ к данным. Класс <xref:System.Xml.XmlDataDocument> сопоставляет XML и реляционные данные в классе ADO.NET <xref:System.Data.DataSet>. Все основанные на платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] приложения могут использовать классы из пространства имен <xref:System.Xml> для доступа и управления, как XML-документами, так и реляционными данными в <xref:System.Xml.XmlDataDocument>. Эта реализация поддерживает многоуровневую архитектуру для сбора и распространения данных. Дополнительные сведения см. в разделе [интеграция XML с реляционными данными и ADO.NET](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md).  
  
## <a name="see-also"></a>См. также  
 [Реализуемых классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
