---
title: XML-литерал CDATA
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 72e899e7bd30f2edf0e88207bb3b75bdf36fa11c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349438"
---
# <a name="xml-cdata-literal-visual-basic"></a>Литеральное представление XML-раздела CDATA (Visual Basic)
Литерал, представляющий объект <xref:System.Xml.Linq.XCData>.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Части  
 `<![CDATA[`  
 Обязательно. Обозначает начало раздела XML CDATA.  
  
 `content`  
 Обязательно. Текстовое содержимое, отображаемое в разделе CDATA XML.  
  
 `]]>`  
 Обязательно. Обозначает конец раздела.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XCData>.  
  
## <a name="remarks"></a>Примечания  
 Разделы XML CDATA содержат необработанный текст, который должен быть добавлен, но не проанализирован, с XML-кодом, содержащим его. Раздел CDATA XML может содержать любой текст. Сюда входят зарезервированные символы XML. Раздел CDATA XML заканчивается последовательностью "]] >". Это подразумевает следующие моменты:  
  
- Нельзя использовать внедренное выражение в XML-литерале CDATA, так как разделители внедренных выражений являются допустимыми содержимым XML CDATA.  
  
- Разделы CDATA XML не могут быть вложенными, так как `content` не могут содержать значение "]] >".  
  
 Можно назначить литерал XML CDATA переменной или включить его в литерал XML-элемента.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк, но не использует символы продолжения строки. Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал CDATA XML в вызов конструктора <xref:System.Xml.Linq.XCData.%23ctor%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается раздел CDATA, содержащий текст "может содержать литеральные \<XML-теги >".  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XCData>
- [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
