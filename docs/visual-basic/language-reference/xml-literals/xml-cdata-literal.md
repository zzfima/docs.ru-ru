---
title: "Литеральное представление XML-раздела CDATA (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
dev_langs:
- VB
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
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
ms.openlocfilehash: 24e52bf203ff3df57e26137da24abcc2cb7e8e20
ms.lasthandoff: 03/13/2017

---
# <a name="xml-cdata-literal-visual-basic"></a>Литеральное представление XML-раздела CDATA (Visual Basic)
Литерал представляет <xref:System.Xml.Linq.XCData>объекта.</xref:System.Xml.Linq.XCData>  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Части  
 `<![CDATA[`  
 Обязательный. Обозначает начало раздела XML CDATA.  
  
 `content`  
 Обязательный. Текст содержимого для отображения в разделе XML CDATA.  
  
 `]]>`  
 Обязательный. Обозначает конец раздела.  
  
## <a name="return-value"></a>Возвращаемое значение  
 <xref:System.Xml.Linq.XCData>Объект.</xref:System.Xml.Linq.XCData>  
  
## <a name="remarks"></a>Примечания  
 Разделы XML CDATA содержит необработанный текст, который должен быть включено, но не проанализировать XML, который его содержит. Раздел XML CDATA может содержать любой текст. Это включает в себя зарезервированные символы XML. Раздел XML CDATA заканчивается последовательностью «]] настроек». Это подразумевает следующее:  
  
-   Нельзя использовать внедренные выражения в литеральном представлении XML CDATA, поскольку разделители внедренного выражения являются допустимым содержимым XML CDATA.  
  
-   Разделы XML CDATA не может быть вложенными, поскольку `content` не может содержать значение «]] настроек».  
  
 Можно присвоить Литеральное представление CDATA XML переменной или включить ее в литерал XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк, но не использует символы продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует XML-раздела CDATA литерала для вызова <xref:System.Xml.Linq.XCData.%23ctor%2A>конструктор.</xref:System.Xml.Linq.XCData.%23ctor%2A>  
  
## <a name="example"></a>Пример  
 В следующем примере создается раздел CDATA, содержащий текст» может содержать литеральное \<XML настроек тегов».  
  
 [!code-vb[VbXMLSamples&#23;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XCData></xref:System.Xml.Linq.XCData>   
 [Литеральное представление XML элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
