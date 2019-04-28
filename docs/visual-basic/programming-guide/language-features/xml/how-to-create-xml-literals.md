---
title: Практическое руководство. Создание XML-литералов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 836ec4390e7675effe57c75c79768272d66925a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775912"
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Практическое руководство. Создание XML-литералов (Visual Basic)
XML документ, фрагмент или элемент можно создать непосредственно в коде с помощью XML-литерала. В примерах в этом разделе показано, как создать элемент XML, содержит три дочерних элемента и способ создания XML-документа.  
  
 Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API-интерфейсы для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>Чтобы создать XML-элемент  
  
- Создайте встроенный XML, используя синтаксис XML, который является таким же, как фактический синтаксис XML.  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     Выполните код. Ниже приведен результат выполнения этого кода.  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Для создания XML-документа  
  
- Создайте встроенный XML-документ. Следующий код создает XML-документ, который имеет синтаксис литерала XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     Выполните код. Ниже приведен результат выполнения этого кода.  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>См. также

- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-литерал элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
