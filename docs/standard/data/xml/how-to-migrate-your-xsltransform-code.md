---
title: Как осуществить перенос кода XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
ms.openlocfilehash: 2bc5cbc1b0857a82d3b0a11f05a4eb5756724546
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710847"
---
# <a name="how-to-migrate-your-xsltransform-code"></a>Как осуществить перенос кода XslTransform
Новые классы XSLT разработаны так, чтобы быть похожими на существующие классы. Класс <xref:System.Xml.Xsl.XslCompiledTransform> заменяет класс <xref:System.Xml.Xsl.XslTransform>. Таблицы стилей компилируются с помощью метода <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>. Преобразования выполняются с помощью метода <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>. В следующей процедуре показаны распространенные XSLT-задачи, а сравнивается код использования классов <xref:System.Xml.Xsl.XslTransform> и <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
### <a name="to-transform-a-file-and-output-to-a-uri"></a>Преобразование файла и вывод в URI  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### <a name="to-compile-a-style-sheet-and-use-a-resolver-with-default-credentials"></a>Компиляция таблицы стилей и использование арбитра с учетными данными по умолчанию  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### <a name="to-use-an-xslt-parameter"></a>Использование параметра XSLT  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### <a name="to-enable-xslt-scripting"></a>Включение XSLT-скриптов  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### <a name="to-load-the-results-into-a-dom-object"></a>Загрузка результатов в объект модели DOM  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
    > [!NOTE]
    > Класс <xref:System.Xml.Xsl.XslCompiledTransform> не имеет метода, возвращающего результаты XSLT-преобразования в виде объекта <xref:System.Xml.XmlReader>. Однако можно сохранить выходные данные в XML-файл и загрузить его в другой объект.  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### <a name="to-stream-the-results-into-another-data-store"></a>Потоковый вывод данных в другое хранилище данных  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslTransform>.  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
- Код с использованием класса <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## <a name="see-also"></a>См. также:

- [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)
- [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
