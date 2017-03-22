---
title: "Функциональное преобразование XML (Visual Basic) | Документы Microsoft"
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
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a188ad5182b757a798f7f29414536ba2d1a88c2b
ms.lasthandoff: 03/13/2017


---
# <a name="functional-transformation-of-xml-visual-basic"></a>Функциональное преобразование XML (Visual Basic)
В этом разделе описан подход с использованием чисто функционального преобразования для изменения XML-документов и производится сравнение его с процедурным подходом.  
  
## <a name="modifying-an-xml-document"></a>Изменение XML-документа  
 Одной из наиболее распространенных задач программиста на XML состоит в том, чтобы преобразовать XML из одной формы в другую. Форма XML-документа представляет собой структуру документа, которая включает:  
  
-   иерархию, выраженную в документе;  
  
-   имена элементов и атрибутов;  
  
-   типы данных элементов и атрибутов.  
  
 В целом наиболее эффективный подход к преобразованию XML из одной формы в другую состоит в чисто функциональном преобразовании. При данном подходе основной задачей программиста будет создать преобразование, которое применяется ко всему XML-документу (к одному или множеству жестко определенных узлов). Функциональное преобразование является, возможно, самым простым для кода (после того как программист приобретет навыки работы с данным подходом), дает наилучший для сопровождения код и часто более компактно, чем другие подходы.  
  
### <a name="xml-functional-transformational-technologies"></a>Технологии функционального преобразования XML  
 Майкрософт предлагает две технологии функционального преобразования для использования в XML-документах: XSLT и LINQ to XML. XSLT поддерживается в <xref:System.Xml.Xsl>управляемое пространство имен и в собственной COM реализации MSXML.</xref:System.Xml.Xsl> Не смотря на то что XSLT представляет собой надежную технологию работы с XML-документами, для ее использования требуется опыт в специализированных областях, а именно в области языка XSLT и поддерживающих его API-интерфейсов.  
  
 В LINQ to XML предусмотрены инструменты, необходимые для чисто функциональных преобразований, кодируемых выразительно и эффективно внутри кода на языках C# и Visual Basic. Например, многие примеры в документации LINQ to XML используют чисто функциональный подход. Кроме того, в [учебника: обработка содержимого документа WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) учебнике мы используем LINQ to XML функциональный подход для управления сведениями в документе Microsoft Word.  
  
 Для более полного сравнения LINQ to XML с другими технологиями Microsoft XML, в разделе [LINQ to XML или. Другие технологии XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 XSLT - это рекомендованный инструмент для преобразований, ориентированных на работу с документами, когда исходный документ имеет неправильную структуру. Несмотря на это, LINQ to XML также может осуществлять преобразования, ориентированные на работу с документами. Дополнительные сведения см. в разделе [Практическое руководство: использование примечаний для преобразования деревьев LINQ to XML в стиль XSLT (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>См. также  
 [Введение в чисто функциональные преобразования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)   
 [Сравнение LINQ to XML с Другие технологии XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)   
 [Сравнение LINQ to XML с другими XML-технологиями](http://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)
