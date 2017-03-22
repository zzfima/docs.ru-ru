---
title: "Пробелы в XML-литералах (Visual Basic) | Документы Microsoft"
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
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b98a88696f24cc0b95401812471d13acea4faa6d
ms.lasthandoff: 03/13/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a>Пробелы в XML-литералах (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор включает только значащие символы пробелов из XML-литерала при создании [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объекта. Незначащие пробелы не включены.  
  
## <a name="significant-and-insignificant-white-space"></a>Значащие и незначащие пробелы  
 Пробелы в XML-литералах учитываются только в трех областях:  
  
-   Когда они находятся в значении атрибута.  
  
-   Когда они являются частью текста содержимого элемента и текст также содержит другие символы.  
  
-   Когда они находятся во встроенном выражении текстовое содержимое элемента.  
  
 В противном случае, компилятор считает незначащие пробельные символы и не включает его в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объекта для литерала.  
  
 Чтобы включить незначащие пробелы в XML-литерал, используйте встроенное выражение, которое содержит строковый литерал с пробелом.  
  
> [!NOTE]
>  Если `xml:space` атрибут отображается в XML-литерал, элемент [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор включает атрибут в <xref:System.Xml.Linq.XElement>объект, но добавление этого атрибута не изменяет способ обработки пробелов компилятором.</xref:System.Xml.Linq.XElement>  
  
## <a name="examples"></a>Примеры  
 Следующий пример содержит два элемента XML, внешний и внутренний. Оба этих элемента содержат пробелы в текстовом содержимом. Пробелы во внешнем элементе незначительна, так как он содержит только пробелы и XML-элемента. Пробелы в внутреннего элемента имеет значение, поскольку он содержит пробелы и текст.  
  
 [!code-vb[VbXMLSamples&#29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 При выполнении этот код выводит следующий текст.  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
