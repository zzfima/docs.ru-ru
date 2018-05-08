---
title: Литеральное представление XML-раздела CDATA (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 999531d8146748fe491255663f0d2d17d056bcd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xml-cdata-literal-visual-basic"></a>Литеральное представление XML-раздела CDATA (Visual Basic)
Объект литерал, представляющий <xref:System.Xml.Linq.XCData> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Части  
 `<![CDATA[`  
 Обязательно. Обозначает начало раздела XML CDATA.  
  
 `content`  
 Обязательно. Текст содержимого для отображения в разделе XML CDATA.  
  
 `]]>`  
 Обязательно. Обозначает конец раздела.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Примечания  
 Разделы XML CDATA содержит необработанный текст, который должны быть включены, но не синтаксического анализа XML, он содержит. Раздел XML CDATA может содержать любой текст. Это включает в себя зарезервированные символы XML. Раздел XML CDATA заканчивается последовательностью «]] >». Это подразумевает следующее:  
  
-   Нельзя использовать внедренное выражение в представлении XML CDATA, поскольку разделители внедренного выражения являются допустимым содержимым XML CDATA.  
  
-   Разделы XML CDATA не может быть вложенными, поскольку `content` не может содержать значение «]] >».  
  
 Можно присвоить переменной литеральное представление CDATA XML или включить ее в литерале XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк, но не использует символы продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.  
  
 Компилятор Visual Basic литерала CDATA XML преобразуется в вызов <xref:System.Xml.Linq.XCData.%23ctor%2A> конструктор.  
  
## <a name="example"></a>Пример  
 В следующем примере создается раздел CDATA, содержащий текст «может содержать литеральное \<XML > теги».  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XCData>  
 [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
