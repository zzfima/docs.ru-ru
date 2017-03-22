---
title: "Сохранение пробелов при загрузке или синтаксическом анализе XML2 | Документы Microsoft"
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
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 39e4270acc0e9a9df5c3855f8c087f41d9612197
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Сохранение пробелов при загрузке и анализе XML
В этом разделе показан способ управления тем, как обрабатываются пробелы в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами. При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева. Это поведение [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] по умолчанию.  
  
 Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами. Эти отступы ни в коем случае изменять нельзя. Для этого в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.  
  
 В этом разделе описывается, как методы, заполняющие XML-деревья, обрабатывают пробелы. Сведения об управлении пробелами при сериализации XML-деревьев см. в разделе [Сохранение пробелов при сериализации](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Поведение методов, заполняющих XML-деревья  
 Следующие методы в <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XDocument>классы заполнение дерева XML.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Можно заполнить дерево XML из файла, <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader>, или строка:</xref:System.Xml.XmlReader> </xref:System.IO.TextReader>  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>  
  
 Если метод не принимает <xref:System.Xml.Linq.LoadOptions>как аргумент, не будет сохранять незначащие пробелы.</xref:System.Xml.Linq.LoadOptions>  
  
 В большинстве случаев, если метод принимает <xref:System.Xml.Linq.LoadOptions>как аргумент, позволяет сохранять незначащие пробелы в XML-дереве как текстовые узлы.</xref:System.Xml.Linq.LoadOptions> Однако если метод загружает XML из <xref:System.Xml.XmlReader>, то <xref:System.Xml.XmlReader>определяет, будет ли сохраняться пробелы или нет.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> Параметр <xref:System.Xml.Linq.LoadOptions>не повлияет.</xref:System.Xml.Linq.LoadOptions>  
  
 С помощью этих методов, если пробелы сохраняются незначащие пробелы вставляется в XML-дерево как <xref:System.Xml.Linq.XText>узлов.</xref:System.Xml.Linq.XText> Если же пробелы не сохраняются, то вставка текстовых узлов не происходит.  
  
 Можно создать XML-дерево с помощью <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> Узлы, которые записываются в <xref:System.Xml.XmlWriter>вставляются в дерево.</xref:System.Xml.XmlWriter> Однако при построении XML-дерева при помощи этого метода сохраняются все методы, независимо от того, содержит ли узел пробел или нет, является ли пробел значащим или нет.  
  
## <a name="see-also"></a>См. также  
 [Синтаксический анализ XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
