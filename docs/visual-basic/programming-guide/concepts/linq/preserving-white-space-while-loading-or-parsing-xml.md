---
title: Сохранение пробелов при загрузке или синтаксическом анализе XML2
ms.date: 07/20/2015
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
ms.openlocfilehash: 3341bfae8ff9de5e17ba18273c60b525f77bff16
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42908167"
---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Сохранение пробелов при загрузке и анализе XML
В этом разделе показан способ управления тем, как обрабатываются пробелы в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами. При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева. Это поведение [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] по умолчанию.  
  
 Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами. Эти отступы ни в коем случае изменять нельзя. Для этого в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.  
  
 В этом разделе описывается, как методы, заполняющие XML-деревья, обрабатывают пробелы. Сведения об управлении пробелами при сериализации деревьев XML см. в разделе [Сохранение пробелов при сериализации](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Поведение методов, заполняющих XML-деревья  
 Следующие методы в классах <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XDocument> заполняют XML-дерево. XML-дерево можно заполнить из файла, объекта <xref:System.IO.TextReader>, объекта <xref:System.Xml.XmlReader> или строки:  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
  
 Если метод не принимает объект <xref:System.Xml.Linq.LoadOptions> в качестве аргумента, то не будет сохранять незначащие пробелы.  
  
 В большинстве случаев, если метод принимает объект <xref:System.Xml.Linq.LoadOptions> в качестве аргумента, позволяет сохранять незначащие пробелы в XML-дереве как текстовые узлы. Однако если метод загружает XML из объекта <xref:System.Xml.XmlReader>, то объект <xref:System.Xml.XmlReader> определяет, будут ли сохраняться пробелы или нет. Задание параметра <xref:System.Xml.Linq.LoadOptions.PreserveWhitespace> не оказывает никакого воздействия.  
  
 Если при использовании этих методов сохраняются незначащие пробелы, то вставляются в XML-дерево как узлы <xref:System.Xml.Linq.XText>. Если же пробелы не сохраняются, то вставка текстовых узлов не происходит.  
  
 XML-дерево можно создать при помощи объекта <xref:System.Xml.XmlWriter>. Узлы, которые записываются в <xref:System.Xml.XmlWriter>, вставляются в дерево. Однако при построении XML-дерева при помощи этого метода сохраняются все методы, независимо от того, содержит ли узел пробел или нет, является ли пробел значащим или нет.  
  
## <a name="see-also"></a>См. также  
 [Синтаксический анализ XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
