---
title: "Сериализация в файлы, объекты TextWriters и XmlWriters3"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f4c5578bc20f91eb35f78355dff0fc4c44e878e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
