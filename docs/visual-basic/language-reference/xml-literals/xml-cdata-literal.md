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
ms.openlocfilehash: 71769c023ba77d40099ba0ba29ef363091e96831
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521560"
---
# <a name="xml-cdata-literal-visual-basic"></a>Литеральное представление XML-раздела CDATA (Visual Basic)
Объект литерал, представляющий <xref:System.Xml.Linq.XCData> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Части  
 `<![CDATA[`  
 Обязательный. Обозначает начало раздела XML CDATA.  
  
 `content`  
 Обязательный. Текстовое содержимое в XML-раздела CDATA.  
  
 `]]>`  
 Обязательный. Обозначает конец раздела.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Примечания  
 Разделы XML CDATA содержит необработанный текст, который должен быть включено, но не синтаксический анализ, XML, он содержится. Раздел XML CDATA может содержать любой текст. Это включает в себя зарезервированные символы XML. Раздел XML CDATA заканчивается последовательность «]] >». Это подразумевает следующее:  
  
-   Нельзя использовать внедренное выражение в представлении XML CDATA, поскольку разделители внедренного выражения являются допустимым содержимым XML CDATA.  
  
-   Разделы XML CDATA не могут быть вложенными, так как `content` не может содержать значение «]] >».  
  
 Можно присвоить переменной в представлении XML CDATA или включить его в литерале XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк, но не использует символы продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.  
  
 Компилятор Visual Basic литерала CDATA XML преобразуется в вызов <xref:System.Xml.Linq.XCData.%23ctor%2A> конструктор.  
  
## <a name="example"></a>Пример  
 В следующем примере создается раздел CDATA, содержащий текст «может содержать литерал \<XML > теги».  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Xml.Linq.XCData>
- [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
