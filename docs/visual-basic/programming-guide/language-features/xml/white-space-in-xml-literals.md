---
title: Пробелы в XML-литералах
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 56ededeb12d07e979bc86b03924e1ae0f0432822
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336006"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Пробелы в XML-литералах (Visual Basic)
Компилятор Visual Basic включает только значащие символы пробела из XML-литерала при создании объекта [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Незначащие символы пробела не включаются.  
  
## <a name="significant-and-insignificant-white-space"></a>Значительные и незначащие пробелы  
 Символы пробелов в XML-литералах являются значимыми только в трех областях:  
  
- Если они находятся в значении атрибута.  
  
- Если они являются частью текстового содержимого элемента, а текст также содержит другие символы.  
  
- Если они находятся в внедренном выражении для текстового содержимого элемента.  
  
 В противном случае компилятор считает символы пробела незначащими и не включает в объект [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] для литерала.  
  
 Чтобы включить незначащие пробелы в XML-литерал, используйте внедренное выражение, содержащее строковый литерал с пробелом.  
  
> [!NOTE]
> Если атрибут `xml:space` отображается в литерале XML-элемента, компилятор Visual Basic включает атрибут в объект <xref:System.Xml.Linq.XElement>, но добавление этого атрибута не влияет на то, как компилятор обрабатывает пробелы.  
  
## <a name="examples"></a>Примеры  
 В следующем примере содержатся два XML-элемента: OUTER и Inner. Оба элемента содержат пробелы в текстовом содержимом. Пробелы во внешнем элементе являются незначащими, так как содержат только пробелы и XML-элементы. Пробел во внутреннем элементе важен, так как он содержит пробелы и текст.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 При запуске этот код отображает следующий текст.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>См. также:

- [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
