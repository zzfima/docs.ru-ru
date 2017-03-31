---
title: "Сохранение пробелов при загрузке и анализе XML | Документы Майкрософт"
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
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
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
ms.openlocfilehash: 1b2ec9b5b1bbc343fde5c9527c1e4f4ad7f14796
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Сохранение пробелов при загрузке и анализе XML
В этом разделе показан способ управления тем, как обрабатываются пробелы в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами. При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева. Это поведение [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] по умолчанию.  
  
 Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами. Эти отступы ни в коем случае изменять нельзя. Для этого в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.  
  
 В этом разделе описывается, как методы, заполняющие XML-деревья, обрабатывают пробелы. Сведения об управлении пробелами при сериализации деревьев XML см. в разделе [Сохранение пробелов при сериализации](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Поведение методов, заполняющих XML-деревья  
 Перечисленные ниже методы в классах <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XDocument> заполняют дерево XML. Дерево XML можно заполнить из файла, объекта <xref:System.IO.TextReader>, объекта <xref:System.Xml.XmlReader> или строки:  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>  
  
 Если метод не принимает объект <xref:System.Xml.Linq.LoadOptions> в качестве аргумента, то он не будет сохранять незначащие пробелы.  
  
 В большинстве случаев, если метод принимает объект <xref:System.Xml.Linq.LoadOptions> в качестве аргумента, то при необходимости можно сохранять незначащие пробелы в дереве XML как текстовые узлы. Однако если метод загружает XML из объекта <xref:System.Xml.XmlReader>, то объект <xref:System.Xml.XmlReader> определяет, будут сохраняться пробелы или нет. Задание параметра <xref:System.Xml.Linq.LoadOptions> не оказывает никакого воздействия.  
  
 Если при использовании этих методов незначащие пробелы сохраняются, то они вставляются в дерево XML как узлы <xref:System.Xml.Linq.XText>. Если же пробелы не сохраняются, то вставка текстовых узлов не происходит.  
  
 Дерево XML можно создать с помощью объекта <xref:System.Xml.XmlWriter>. Узлы, которые записываются в <xref:System.Xml.XmlWriter>, вставляются в дерево. Однако при построении XML-дерева при помощи этого метода сохраняются все методы, независимо от того, содержит ли узел пробел или нет, является ли пробел значащим или нет.  
  
## <a name="see-also"></a>См. также  
 [Анализ XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
