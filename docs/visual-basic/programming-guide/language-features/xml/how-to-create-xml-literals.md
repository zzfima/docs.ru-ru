---
title: Практическое руководство. Создание XML-литералов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e5f8429b3ff02678bf8bf3e9e32bef6eb1a56831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Практическое руководство. Создание XML-литералов (Visual Basic)
Можно создать документ, фрагмент или элемент XML непосредственно в коде с помощью XML-литерала. Примеры в этом разделе демонстрируют способ создания XML-элемента, который имеет три дочерних элемента и способ создания XML-документа.  
  
 Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>Чтобы создать XML-элемент  
  
-   Создайте встроенный XML, используя синтаксис XML-литерала, который совпадает с фактическим синтаксисом XML.  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     Выполните код. Результат выполнения этого кода является:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Для создания XML-документа  
  
-   Создайте встроенный XML-документ. Следующий код создает XML-документ, который имеет синтаксис литералов, XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     Выполните код. Результат выполнения этого кода является:  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>См. также  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
