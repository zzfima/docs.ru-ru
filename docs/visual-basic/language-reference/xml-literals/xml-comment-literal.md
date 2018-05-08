---
title: XML-литерал комментариев (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 60c354215c627683fd6c69d9ca66fc115c26ccda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xml-comment-literal-visual-basic"></a>XML-литерал комментариев (Visual Basic)
Объект литерал, представляющий <xref:System.Xml.Linq.XComment> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`<!--`|Обязательно. Обозначает начало комментария XML.|  
|`content`|Обязательно. Текст, отображаемый в комментарии XML. Не может содержать последовательность двух дефисов (--) или заканчиваться дефисом рядом закрывающий тег.|  
|`-->`|Обязательно. Обозначает конец комментария XML.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Примечания  
 XML-литералы комментариев не содержат содержимого документа. они содержат сведения о документе. Раздел комментария XML заканчивается последовательностью «-->». Это подразумевает следующее:  
  
-   Нельзя использовать внедренное выражение в XML-литерал комментария, поскольку разделители внедренного выражения являются допустимым содержимым комментария XML.  
  
-   Разделы комментария XML не может быть вложенными, поскольку `content` не может содержать значение «-->».  
  
 XML-литерал комментария можно присвоить переменной, или его можно включить в литерале XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.  
  
 Компилятор Visual Basic преобразует XML-литерал комментария в вызов <xref:System.Xml.Linq.XComment.%23ctor%2A> конструктор.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-комментарий, содержащее текст «Это комментарий».  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XComment>  
 [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
