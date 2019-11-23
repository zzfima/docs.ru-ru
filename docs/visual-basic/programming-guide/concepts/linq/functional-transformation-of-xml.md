---
title: Функциональное преобразование XML
ms.date: 07/20/2015
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
ms.openlocfilehash: 7e029fd562ae3f221a8aaef40f332a1e3fa896eb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353427"
---
# <a name="functional-transformation-of-xml-visual-basic"></a>Functional Transformation of XML (Visual Basic)
В этом разделе описан подход с использованием чисто функционального преобразования для изменения XML-документов и производится сравнение его с процедурным подходом.  
  
## <a name="modifying-an-xml-document"></a>Изменение XML-документа  
 Одной из наиболее распространенных задач программиста на XML состоит в том, чтобы преобразовать XML из одной формы в другую. Форма XML-документа представляет собой структуру документа, которая включает:  
  
- иерархию, выраженную в документе;  
  
- имена элементов и атрибутов;  
  
- типы данных элементов и атрибутов.  
  
 В целом наиболее эффективный подход к преобразованию XML из одной формы в другую состоит в чисто функциональном преобразовании. При данном подходе основной задачей программиста будет создать преобразование, которое применяется ко всему XML-документу (к одному или множеству жестко определенных узлов). Функциональное преобразование является, возможно, самым простым для кода (после того как программист приобретет навыки работы с данным подходом), дает наилучший для сопровождения код и часто более компактно, чем другие подходы.  
  
### <a name="xml-functional-transformational-technologies"></a>Технологии функционального преобразования XML  
 Майкрософт предлагает две технологии функционального преобразования для использования в XML-документах: XSLT и LINQ to XML. XSLT поддерживается в управляемом пространстве имен <xref:System.Xml.Xsl>, а также в собственной COM реализации MSXML. Не смотря на то что XSLT представляет собой надежную технологию работы с XML-документами, для ее использования требуется опыт в специализированных областях, а именно в области языка XSLT и поддерживающих его API-интерфейсов.  
  
 В LINQ to XML предусмотрены инструменты, необходимые для чисто функциональных преобразований, кодируемых выразительно и эффективно внутри кода на языках C# и Visual Basic. Например, многие примеры в документации LINQ to XML используют чисто функциональный подход. Also, in the [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial, we use LINQ to XML in a functional approach to manipulate information in a Microsoft Word document.  
  
 For a more complete comparison of LINQ to XML with other Microsoft XML technologies, see [LINQ to XML vs. Other XML Technologies](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 XSLT - это рекомендованный инструмент для преобразований, ориентированных на работу с документами, когда исходный документ имеет неправильную структуру. Несмотря на это, LINQ to XML также может осуществлять преобразования, ориентированные на работу с документами. For more information, see [How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>См. также

- [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [LINQ to XML vs. Other XML Technologies](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
