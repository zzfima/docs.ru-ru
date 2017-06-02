---
title: "Как осуществить перенос кода XslTransform | Microsoft Docs"
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
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Как осуществить перенос кода XslTransform
Новые классы XSLT разработаны так, чтобы быть похожими на существующие классы.  Класс <xref:System.Xml.Xsl.XslCompiledTransform> заменяет класс <xref:System.Xml.Xsl.XslTransform>.  Таблицы стилей компилируются с помощью метода <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  Преобразования выполняются с помощью метода <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  В следующей процедуре показаны распространенные XSLT\-задачи, а сравнивается код использования классов <xref:System.Xml.Xsl.XslTransform> и <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
### Преобразование файла и вывод в URI  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### Компиляция таблицы стилей и использование арбитра с учетными данными по умолчанию  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### Использование параметра XSLT  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### Включение XSLT\-скриптов  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### Загрузка результатов в объект модели DOM  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
    > [!NOTE]
    >  Класс <xref:System.Xml.Xsl.XslCompiledTransform> не имеет метода, возвращающего результаты XSLT\-преобразования в виде объекта <xref:System.Xml.XmlReader>.  Однако можно сохранить выходные данные в XML\-файл и загрузить его в другой объект.  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### Потоковый вывод данных в другое хранилище данных  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
-   Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## См. также  
 [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)   
 [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)