---
title: Пробелы в XML-литералах (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 60ee90c69aeda38f95107a6043801a4994972079
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245163"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Пробелы в XML-литералах (Visual Basic)
Компилятор Visual Basic включает только символы значащих пробелов из XML-литерала, при создании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта. Незначащие пробелы не включены.  
  
## <a name="significant-and-insignificant-white-space"></a>Значащий и незначащий пробел  
 Пробелы в XML-литералах значимы только в трех областях:  
  
-   Когда они находятся в значении атрибута.  
  
-   Когда они являются частью содержимого текстового элемента и текст также содержит другие символы.  
  
-   Когда они находятся во внедренном выражении для текстового содержимого элемента.  
  
 В противном случае компилятор считает незначащие пробелы и не включает его в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта для литерала.  
  
 Чтобы включить незначащие пробелы в XML-литерал, используйте встроенное выражение, которое содержит строковый литерал с пробелом.  
  
> [!NOTE]
>  Если `xml:space` атрибут содержится в литерале XML-элемента, компилятор Visual Basic включает атрибут в <xref:System.Xml.Linq.XElement> объект, но добавление этого атрибута не изменяет способ обработки пробелов компилятором.  
  
## <a name="examples"></a>Примеры  
 Следующий пример содержит два элемента XML, внешними и внутренними. Оба этих элемента содержат пробелы в текстовом содержимом. Пустое пространство во внешнем элементе не играет роли, так как он содержит только пробелы и XML-элемента. Пустое пространство во внутреннем элементе важен, так как он содержит пробел и текст.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 При запуске этот код отображает следующий текст.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
