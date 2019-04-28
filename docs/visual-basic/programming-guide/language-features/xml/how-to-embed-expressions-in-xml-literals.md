---
title: Практическое руководство. Внедрить выражения в XML-литералах (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 31e79a8787978ffab2e35cd2827b80a8f1ed843e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61861365"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Практическое руководство. Внедрить выражения в XML-литералах (Visual Basic)
XML-литералов можно объединить с внедренными выражениями для создания документа XML, фрагмент или элемент, содержащий содержимое, созданное во время выполнения. Следующие примеры демонстрируют, как использовать внедренные выражения для заполнения содержимого элемента, атрибутов и имена элементов во время выполнения.  
  
 Для внедренного выражения используется синтаксис `<%=` `exp` `%>`, который является такой же синтаксис, [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] использует. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API-интерфейсы для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов. Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-insert-text-as-element-content"></a>Для вставки текста в качестве содержимого элемента  
  
- В следующем примере показано, как вставить текст, содержащийся в `contactName` переменной между открывающей и закрывающей имен элементов.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Для вставки текста в качестве значения атрибута  
  
- В следующем примере показано, как вставить текст, содержащийся в `phoneType` переменной в качестве значения `type` атрибута.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Для вставки текста для имени элемента  
  
- В следующем примере показано, как вставить текст, содержащийся в `elementName` переменной в качестве имени элемента.  
  
     При создании элементов при использовании этого метода, необходимо закрыть их с помощью \</ > тег.  
  
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
