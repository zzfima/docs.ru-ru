---
title: Входные данные для класса XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 834049f1-ab41-449e-9f10-4a1d0701bc48
ms.openlocfilehash: 9aae85aa4516dc0555e959358ba1b7db3002145d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710743"
---
# <a name="inputs-to-the-xslcompiledtransform-class"></a>Входные данные для класса XslCompiledTransform
Метод <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> принимает три входных типа для документа источника: объект, реализующий интерфейс <xref:System.Xml.XPath.IXPathNavigable>, объект <xref:System.Xml.XmlReader>, который считывает документ источника, и строку URI.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslCompiledTransform> сохраняет пробелы по умолчанию. Это соответствует разделу [3.4 рекомендации W3C XSLT 1.0](https://www.w3.org/TR/xslt.html#strip).  
  
## <a name="ixpathnavigable-interface"></a>Интерфейс IXPathNavigable  
 Интерфейс <xref:System.Xml.XPath.IXPathNavigable> реализован в классах <xref:System.Xml.XmlNode> и <xref:System.Xml.XPath.XPathDocument>. Эти классы представляют хранящийся в памяти кэш XML-данных.  
  
- Класс <xref:System.Xml.XmlNode> основан на модели W3C DOM и позволяет вносить изменения.  
  
- Класс <xref:System.Xml.XPath.XPathDocument> представляет собой доступное только для чтения хранилище данных на основе модели данных XPath. Класс <xref:System.Xml.XPath.XPathDocument> рекомендуется для обработки XSLT. Он обеспечивает более высокую производительность по сравнению с классом <xref:System.Xml.XmlNode>.  
  
> [!NOTE]
> Преобразования применяются к документу в целом. Иными словами, если передать узел, отличный от корневого узла документа, это не помешает процессу преобразования обратиться ко всем узлам загружаемого документа. Чтобы преобразовать фрагмент узла, необходимо создать объект, содержащий только фрагмент этого узла, и передать его методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>. См. дополнительные сведения о [преобразовании фрагментов узлов](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md).  
  
 В следующем примере метод <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> используется для преобразования файла books.xml в books.html с помощью таблицы стилей transform.xsl. Файлы books.xml и transform.xsl можно найти в руководстве по [преобразованию XSLT с использованием сборки](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#1)]
 [!code-vb[XslCompiledTransform.Transform2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#1)]  
  
## <a name="xmlreader-object"></a>Объект XmlReader  
 Метод <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> загружает из текущего узла объекта <xref:System.Xml.XmlReader> всех его потомков. Это позволяет использовать фрагмент документа в качестве контекстного документа. После возвращения метода <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> объект <xref:System.Xml.XmlReader> позиционируется на следующем узле за контекстным документом. По достижении конца документа объект <xref:System.Xml.XmlReader> позиционируется в конец файла (EOF).  
  
 В следующем примере метод <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> используется для преобразования файла books.xml в books.html с помощью таблицы стилей transform.xsl. Файлы books.xml и transform.xsl можно найти в руководстве по [преобразованию XSLT с использованием сборки](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#2)]
 [!code-vb[XslCompiledTransform.Transform2#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#2)]  
  
## <a name="string-uri"></a>Строковые URI  
 Можно также указать URI исходного документа в виде входных данных XSLT. Для разрешения URI используется объект <xref:System.Xml.XmlResolver>. Чтобы использовать объект <xref:System.Xml.XmlResolver>, нужно передать его методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>. Если объект <xref:System.Xml.XmlResolver> не указан, метод <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> использует объект <xref:System.Xml.XmlUrlResolver> по умолчанию без учетных данных.  
  
 В следующем примере метод <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType> используется для преобразования файла books.xml в books.html с помощью таблицы стилей transform.xsl. Файлы books.xml и transform.xsl можно найти в руководстве по [преобразованию XSLT с использованием сборки](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#3)]
 [!code-vb[XslCompiledTransform.Transform2#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#3)]  
  
 См. дополнительные сведения о [разрешении внешних ресурсов в ходе обработки XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md).  
  
## <a name="see-also"></a>См. также:

- [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
