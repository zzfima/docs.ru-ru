---
title: "Сериализация в файлы и объекты TextWriters и XmlWriters3 | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 98662b8d84459ed051d048084c2755fa7aaf8247
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Сериализация в файлы и объекты TextWriters и XmlWriters
Можно сериализовать XML-деревья в <xref:System.IO.File>, <xref:System.IO.TextWriter>, или <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File>  
  
 Можно сериализовать любой компонент XML, включая <xref:System.Xml.Linq.XDocument>и <xref:System.Xml.Linq.XElement>, в строку с помощью `ToString` метод.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
 Если необходимо отключить форматирование при сериализации в строку, можно использовать <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>метода.</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>  
  
 Установка9600 поведение при сериализации для файла состоит в форматировании (посредством создания отступов) результирующего XML-документа. При создании отступов не имеющие значения пробелы в XML-дереве не сохраняются. Для выполнения сериализации с форматированием, используйте одну из перегрузок следующих методов, которые не принимают <xref:System.Xml.Linq.SaveOptions>в качестве аргумента:</xref:System.Xml.Linq.SaveOptions>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Если необходимо воздержаться от создания отступов и сохранять незначащие пробелы в XML-дерево, используйте одну из перегрузок следующих методов, принимающих <xref:System.Xml.Linq.SaveOptions>в качестве аргумента:</xref:System.Xml.Linq.SaveOptions>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Примеры см. в следующем разделе справки.  
  
## <a name="see-also"></a>См. также  
 [Сериализация деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
