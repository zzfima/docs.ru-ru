---
title: Практическое руководство. Внедрение выражений в XML-литералы
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 2e8dd10b334b0271e3c9de11ed155c9d5d7aae48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332931"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)
Литералы XML можно объединять с внедренными выражениями для создания XML-документа, фрагмента или элемента, содержащего содержимое, созданное во время выполнения. В следующих примерах показано, как использовать внедренные выражения для заполнения содержимого, атрибутов и имен элементов во время выполнения.  
  
 Синтаксис для внедренного выражения `<%=` `exp` `%>`— тот же синтаксис, который ASP.NET использует. Дополнительные сведения см. [в разделе внедренные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов также можно использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] интерфейсы API. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-insert-text-as-element-content"></a>Вставка текста в качестве содержимого элемента  
  
- В следующем примере показано, как вставить текст, содержащийся в переменной `contactName`, между открывающим и закрывающим элементами Name.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Вставка текста в качестве значения атрибута  
  
- В следующем примере показано, как вставить текст, содержащийся в переменной `phoneType`, в качестве значения атрибута `type`.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Вставка текста для имени элемента  
  
- В следующем примере показано, как вставить текст, содержащийся в переменной `elementName`, в качестве имени элемента.  
  
     При создании элементов с помощью этого метода их необходимо закрыть с помощью тега \</>.  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание XML-литералов](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
