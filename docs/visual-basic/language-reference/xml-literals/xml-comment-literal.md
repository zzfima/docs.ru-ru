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
ms.openlocfilehash: 91369392f33f2a86a7a4cb5ffb3faa668c113348
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965402"
---
# <a name="xml-comment-literal-visual-basic"></a>XML-литерал комментариев (Visual Basic)
Литерал, представляющий <xref:System.Xml.Linq.XComment> объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`<!--`|Обязательный. Обозначает начало XML-комментария.|  
|`content`|Обязательный. Текст, отображаемый в XML-комментарии. Не может содержать последовательность из двух дефисов (--) или заканчиваться дефисом, рядом с закрывающим тегом.|  
|`-->`|Обязательный. Обозначает конец XML-комментария.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Примечания  
 Литералы XML-комментариев не содержат содержимого документа; они содержат сведения о документе. Раздел комментария XML заканчивается последовательностью "-->". Это подразумевает следующие моменты:  
  
- Нельзя использовать внедренное выражение в литерале XML-комментария, так как разделители внедренных выражений являются допустимым содержимым XML-комментариев.  
  
- Разделы комментариев XML не могут быть вложенными `content` , поскольку не могут содержать значение "-->".  
  
 Литерал комментария XML можно назначить переменной или включить в литерал XML-элемента.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк без использования символов продолжения строки. Эта функция позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал XML-комментария в вызов <xref:System.Xml.Linq.XComment.%23ctor%2A> конструктора.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-комментарий, содержащий текст "это комментарий".  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XComment>
- [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
