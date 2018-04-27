---
title: Литерал инструкции обработки XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d2df93a46d426358988b3ad7f3161c7ae0c7b9e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Литерал инструкции обработки XML (Visual Basic)
Объект литерал, представляющий <xref:System.Xml.Linq.XProcessingInstruction> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Части  
 `<?`  
 Обязательно. Обозначает начало литерала инструкции обработки XML.  
  
 `piName`  
 Обязательно. Имя, указывающее, какое приложение инструкции обработки. Не может начинаться с «xml» или «XML».  
  
 `piData`  
 Необязательный. Строка, указывающая, как приложение распространяется `piName` должен обрабатывать XML-документ.  
  
 `?>`  
 Обязательно. Обозначает конец инструкции обработки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Примечания  
 XML литералы инструкции обработки указывают, как приложения должны обрабатывать XML-документа. Когда приложение загружает XML-документ, приложение может проверить инструкции обработки XML, чтобы определить способ обработки документа. Приложение интерпретирует значение `piName` и `piData`.  
  
 XML-литерала документа использует синтаксис, аналогичный синтаксису инструкции по обработке XML. Дополнительные сведения см. в разделе [литерала документа XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  `piName` Элемент не может начинаться со строки «xml» или «XML», так как спецификации XML 1.0 резервирует эти идентификаторы.  
  
 Можно назначить литерал инструкции обработки XML переменной или включить ее в литерал XML-документа.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без использования символа продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.  
  
 Компилятор Visual Basic литерала инструкции обработки XML преобразуется в вызов <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> конструктор.  
  
## <a name="example"></a>Пример  
 В следующем примере создается определение таблицы стилей для XML-документ инструкцию по обработке.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
