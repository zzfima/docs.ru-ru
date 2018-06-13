---
title: Пробелы в XML-литералах (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 60ee90c69aeda38f95107a6043801a4994972079
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649754"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Пробелы в XML-литералах (Visual Basic)
Компилятор Visual Basic включает только значимые пробелы символы из XML-литерала при создании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта. Незначащие пробелы не включены.  
  
## <a name="significant-and-insignificant-white-space"></a>Значащие и незначащие пробелы  
 Пробелы в XML-литералах значимыми являются только в трех областях:  
  
-   Когда они находятся в значении атрибута.  
  
-   Если они являются частью текстового содержимого элемента и текст также содержит другие символы.  
  
-   Когда они находятся во внедренном выражении для текстового содержимого элемента.  
  
 В противном случае компилятор считает незначащие пробельные символы и не включает его в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта для литерала.  
  
 Чтобы включить незначащие пробелы в XML-литерал, используйте внедренное выражение, содержит строковый литерал с пробелом.  
  
> [!NOTE]
>  Если `xml:space` атрибут отображается в литерале XML-элемента, компилятор Visual Basic включает атрибут в <xref:System.Xml.Linq.XElement> объект, но добавление этого атрибута не изменяет способ обработки пробелов компилятором.  
  
## <a name="examples"></a>Примеры  
 Следующий пример содержит два элемента XML, внешнее и внутреннее. Оба этих элемента содержат пробелы в текстовом содержимом. Свободное пространство на внешний элемент не важна, так как он содержит только пробелы и XML-элемента. Пробелы в внутреннего элемента имеет значение, поскольку он содержит пробелы и текст.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 При выполнении этот код выводит следующий текст.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
