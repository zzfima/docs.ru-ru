---
title: XML-литерал комментария
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 8d9db66aabe344bd5c8f9a92ac8618b7bc1abb43
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349389"
---
# <a name="xml-comment-literal-visual-basic"></a>XML-литерал комментариев (Visual Basic)
Литерал, представляющий объект <xref:System.Xml.Linq.XComment>.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`<!--`|Обязательно. Обозначает начало XML-комментария.|  
|`content`|Обязательно. Текст, отображаемый в XML-комментарии. Не может содержать последовательность из двух дефисов (--) или заканчиваться дефисом, рядом с закрывающим тегом.|  
|`-->`|Обязательно. Обозначает конец XML-комментария.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Заметки  
 Литералы XML-комментариев не содержат содержимого документа; они содержат сведения о документе. Раздел комментария XML заканчивается последовательностью "-->". Это подразумевает следующие моменты:  
  
- Нельзя использовать внедренное выражение в литерале XML-комментария, так как разделители внедренных выражений являются допустимым содержимым XML-комментариев.  
  
- Разделы комментариев XML не могут быть вложенными, так как `content` не могут содержать значение "-->".  
  
 Литерал комментария XML можно назначить переменной или включить в литерал XML-элемента.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк без использования символов продолжения строки. Эта функция позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал XML-комментария в вызов конструктора <xref:System.Xml.Linq.XComment.%23ctor%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-комментарий, содержащий текст "это комментарий".  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XComment>
- [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
