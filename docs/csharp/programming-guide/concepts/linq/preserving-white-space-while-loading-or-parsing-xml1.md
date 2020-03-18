---
title: Сохранение пробелов при загрузке и анализе XML
ms.date: 07/20/2015
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
ms.openlocfilehash: d015c21813df2224356bb49212fe282fa5372d03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591552"
---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Сохранение пробелов при загрузке и анализе XML
В этой статье показан способ управления тем, как обрабатываются пробелы в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами. При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева. Это поведение [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] по умолчанию.  
  
 Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами. Эти отступы ни в коем случае изменять нельзя. Для этого в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.  
  
 В этой статье описывается, как методы, заполняющие XML-деревья, обрабатывают пробелы. Сведения об управлении пробелами при сериализации деревьев XML см. в разделе [Сохранение пробелов при сериализации](./preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Поведение методов, заполняющих XML-деревья  
 Следующие методы в классах <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XDocument> заполняют XML-дерево. XML-дерево можно заполнить из файла, объекта <xref:System.IO.TextReader>, объекта <xref:System.Xml.XmlReader> или строки:  
  
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
  
 Если метод не принимает объект <xref:System.Xml.Linq.LoadOptions> в качестве аргумента, то не будет сохранять незначащие пробелы.  
  
 В большинстве случаев, если метод принимает объект <xref:System.Xml.Linq.LoadOptions> в качестве аргумента, позволяет сохранять незначащие пробелы в XML-дереве как текстовые узлы. Однако если метод загружает XML из объекта <xref:System.Xml.XmlReader>, то объект <xref:System.Xml.XmlReader> определяет, будут ли сохраняться пробелы или нет. Задание параметра <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> не оказывает никакого воздействия.  
  
 Если при использовании этих методов сохраняются незначащие пробелы, то вставляются в XML-дерево как узлы <xref:System.Xml.Linq.XText>. Если же пробелы не сохраняются, то вставка текстовых узлов не происходит.  
  
 XML-дерево можно создать при помощи объекта <xref:System.Xml.XmlWriter>. Узлы, которые записываются в <xref:System.Xml.XmlWriter>, вставляются в дерево. Однако при построении XML-дерева при помощи этого метода сохраняются все методы, независимо от того, содержит ли узел пробел или нет, является ли пробел значащим или нет.  
  