---
title: "Сохранение пробелов при сериализации | Документы Майкрософт"
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
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
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
ms.openlocfilehash: 1d6cebecd75bedc393b06261c1955a554c9cf18c
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-serializing"></a>Сохранение пробелов при сериализации
В этом разделе описывается управление пробелами при сериализации XML-дерева.  
  
 Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами. При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева. Это поведение [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] по умолчанию.  
  
 Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами. Эти отступы ни в коем случае изменять нельзя. Для этого в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Управление пробелами в методах сериализации XML-деревьев  
 Следующие методы в классах <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XDocument> выполняют сериализацию XML-дерева. XML-дерево можно сериализовать в файл, <xref:System.IO.TextReader>, или <xref:System.Xml.XmlReader>. Метод `ToString` позволяет сериализовать в строку.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName>  
  
 Если метод не принимает объект <xref:System.Xml.Linq.SaveOptions> в качестве аргумента, то он отформатирует сериализованный XML (расставит отступы). В этом случае все незначащие пробелы в XML-дереве удаляются.  
  
 Если метод принимает объект <xref:System.Xml.Linq.SaveOptions> в качестве аргумента, то можно указать, что этот метод не должен форматировать сериализованный XML (расставлять отступы). В этом случае все незначащие пробелы в XML-дереве сохраняются.  
  
## <a name="see-also"></a>См. также  
 [Сериализация XML-деревьев (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
