---
title: "Литерал инструкции (Visual Basic) обработки XML | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
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
ms.openlocfilehash: 2903297fa22cd8dc10bc4b12abaa754d4f6284f2
ms.lasthandoff: 03/13/2017

---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Литерал инструкции обработки XML (Visual Basic)
Литерал представляет <xref:System.Xml.Linq.XProcessingInstruction>объекта.</xref:System.Xml.Linq.XProcessingInstruction>  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Части  
 `<?`  
 Обязательный. Обозначает начало литерал инструкции обработки XML.  
  
 `piName`  
 Обязательный. Имя, указывающее целевое приложение инструкции обработки. Не может начинаться с «xml» или «XML».  
  
 `piData`  
 Необязательный. Строка, указывающая, как приложение мишенью `piName` должен обрабатывать XML-документ.  
  
 `?>`  
 Обязательный. Обозначает конец инструкции обработки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 <xref:System.Xml.Linq.XProcessingInstruction>Объект.</xref:System.Xml.Linq.XProcessingInstruction>  
  
## <a name="remarks"></a>Примечания  
 XML литералы инструкции обработки указывают, как приложения должны обрабатывать XML-документ. Когда приложение загружает XML-документ, оно может проверить инструкции обработки XML для определения способа обработки документа. Приложение интерпретирует значение `piName` и `piData`.  
  
 Литерал XML-документа использует синтаксис, аналогичный, инструкции по обработке XML. Дополнительные сведения см. в разделе [литерала XML документ](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  `piName` Элемент не может начинаться со строки «xml» или «XML», поскольку спецификация XML 1.0 резервирует эти идентификаторы.  
  
 Можно назначить литерал инструкции обработки XML переменной или включить ее в литерал XML-документа.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] программы.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует литерал инструкции обработки XML вызов <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>конструктор.</xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>  
  
## <a name="example"></a>Пример  
 В следующем примере создается инструкцию обработки, определяющая таблицу стилей для XML-документа.  
  
 [!code-vb[VbXMLSamples&#28;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>   
 [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
