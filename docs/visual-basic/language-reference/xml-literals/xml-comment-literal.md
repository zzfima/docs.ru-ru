---
title: "XML-литерал комментария (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralComment
dev_langs:
- VB
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 88cfb984be42345ae1e5c998cf82aa1415d2455e
ms.lasthandoff: 03/13/2017

---
# <a name="xml-comment-literal-visual-basic"></a>XML-литерал комментариев (Visual Basic)
Литерал представляет <xref:System.Xml.Linq.XComment>объекта.</xref:System.Xml.Linq.XComment>  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<!-- content -->  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`<!--`|Обязательный. Обозначает начало комментария XML.|  
|`content`|Обязательный. Текст для отображения в XML-комментарий. Не может содержать ряд двух дефисов (--) или заканчиваться дефисом рядом с закрывающим тегом.|  
|`-->`|Обязательный. Обозначает конец комментария XML.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 <xref:System.Xml.Linq.XComment>Объект.</xref:System.Xml.Linq.XComment>  
  
## <a name="remarks"></a>Примечания  
 XML-литералы комментариев не содержат содержимое документа; они содержат сведения о документе. Раздел комментария XML заканчивается последовательностью «-->». Это подразумевает следующее:  
  
-   Нельзя использовать внедренное выражение в литерале комментария XML, поскольку разделители внедренного выражения являются допустимым содержимым комментария XML.  
  
-   Разделы комментария XML не может быть вложенными, поскольку `content` не может содержать значение «-->».  
  
 XML-литерал комментария можно присвоить переменной, или его можно включить в литерал XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует XML-литерал комментария вызов <xref:System.Xml.Linq.XComment.%23ctor%2A>конструктор.</xref:System.Xml.Linq.XComment.%23ctor%2A>  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-комментарий с текстом «Это комментарий».  
  
 [!code-vb[VbXMLSamples №&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>   
 [Литеральное представление XML элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
