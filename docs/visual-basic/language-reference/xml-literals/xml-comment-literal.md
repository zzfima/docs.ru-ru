---
title: "XML-литерал комментариев (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36be34ac22cfe926a2eea946f5e4c4eb534de696
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
|`content`|Обязательный. Текст, отображаемый в комментарии XML. Не может содержать последовательность двух дефисов (--) или заканчиваться дефисом рядом закрывающий тег.|  
|`-->`|Обязательный. Обозначает конец комментария XML.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XComment>.  
  
## <a name="remarks"></a>Примечания  
 XML-литералы комментариев не содержат содержимого документа. они содержат сведения о документе. Раздел комментария XML заканчивается последовательностью «-->». Это подразумевает следующее:  
  
-   Нельзя использовать внедренное выражение в XML-литерал комментария, поскольку разделители внедренного выражения являются допустимым содержимым комментария XML.  
  
-   Разделы комментария XML не может быть вложенными, поскольку `content` не может содержать значение «-->».  
  
 XML-литерал комментария можно присвоить переменной, или его можно включить в литерале XML-элемента.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Эта функция позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] программы.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Компилятор преобразует XML-литерал комментария вызов <xref:System.Xml.Linq.XComment.%23ctor%2A> конструктор.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-комментарий, содержащее текст «Это комментарий».  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XComment>  
 [XML-литерал элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
