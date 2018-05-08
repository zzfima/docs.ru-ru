---
title: Сериализация в файлы, объекты TextWriters и XmlWriters3
ms.date: 07/20/2015
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
ms.openlocfilehash: ff877e3c800bd1409d796fb68d651175d3602e34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Сериализация в файлы и объекты TextWriters и XmlWriters
XML-деревья можно сериализовать для <xref:System.IO.File>, <xref:System.IO.TextWriter> или для <xref:System.Xml.XmlWriter>.  
  
 Любой компонент XML, включая <xref:System.Xml.Linq.XDocument> и <xref:System.Xml.Linq.XElement>, можно сериализовать для строки с помощью метода `ToString`.  
  
 Если в процессе сериализации в строку необходимо подавить форматирование, эту задачу можно решить с помощью метода <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>.  
  
 При выполнении сериализации для файла характер действий по умолчанию состоит в форматировании результирующего XML-документа посредством создания отступов. При создании отступов не имеющие значения пробелы в XML-дереве не сохраняются. Для выполнения сериализации с форматированием нужно использовать одну из перегрузок следующих методов, не принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 Если необходимо воздержаться от создания отступов и сохранить не имеющие значения пробелы в XML-дереве, нужно использовать одну из перегрузок следующих методов, принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 Примеры см. в следующем разделе справки.  
  
## <a name="see-also"></a>См. также  
 [Сериализация деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
