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
ms.openlocfilehash: 7af01bda05b113be02261051421a91bdea776851
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644573"
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
|`<!--`|Обязательный. Обозначает начало комментария XML.|  
|`content`|Обязательный. Текст, появляющийся в комментарии XML. Не может содержать ряд два дефиса (-) или заканчиваться дефисом рядом закрывающий тег.|  
|`-->`|Обязательный. Обозначает конец комментария XML.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Примечания  
 XML-литералы комментариев не содержат содержимого документа; они содержат сведения о документе. Раздел комментариев XML заканчивается последовательность «-->». Это подразумевает следующее:  
  
- Нельзя использовать внедренное выражение в XML-литерал комментария, поскольку разделители внедренного выражения представляют допустимое содержимое комментария XML.  
  
- Разделы комментария XML не могут быть вложенными, так как `content` не может содержать значение «-->».  
  
 XML-литерал комментария можно присвоить переменной, или ее можно включить в литерале XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.  
  
 Компилятор Visual Basic преобразует XML-литерал комментария в вызов <xref:System.Xml.Linq.XComment.%23ctor%2A> конструктор.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-комментарий, содержащий текст «Это комментарий».  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XComment>
- [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
