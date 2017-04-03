---
title: "Сериализация в файлы и объекты TextWriter и XmlWriter | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f61324395e81509e5800e99b654a8c669d4397f0
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Сериализация в файлы и объекты TextWriters и XmlWriters
XML-деревья можно сериализовать в <xref:System.IO.File>, <xref:System.IO.TextWriter> или <xref:System.Xml.XmlWriter>.  
  
 Любой XML-компонент, включая <xref:System.Xml.Linq.XDocument> и <xref:System.Xml.Linq.XElement>, можно сериализовать в строку с помощью метода `ToString`.  
  
 Если при сериализации в строку необходимо отключить форматирование, можно использовать метод <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>.  
  
 При выполнении сериализации для файла характер действий по умолчанию состоит в форматировании результирующего XML-документа посредством создания отступов. При создании отступов не имеющие значения пробелы в XML-дереве не сохраняются. Для выполнения сериализации с форматированием нужно использовать одну из перегрузок следующих методов, не принимающих <xref:System.Xml.Linq.SaveOptions> в качестве аргумента:  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Если необходимо воздержаться от создания отступов и сохранить не имеющие значения пробелы в XML-дереве, нужно использовать одну из перегрузок следующих методов, принимающих <xref:System.Xml.Linq.SaveOptions> как аргумент:  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Примеры см. в следующем разделе справки.  
  
## <a name="see-also"></a>См. также  
 [Сериализация XML-деревьев (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
