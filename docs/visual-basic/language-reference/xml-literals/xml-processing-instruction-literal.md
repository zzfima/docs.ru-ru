---
title: Литерал инструкции обработки XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3fbb16a4d47801b671d37566573215d3a57afff1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938610"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Литерал инструкции обработки XML (Visual Basic)
Объект литерал, представляющий <xref:System.Xml.Linq.XProcessingInstruction> объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Части  
 `<?`  
 Обязательный. Обозначает начало литерала инструкции обработки XML.  
  
 `piName`  
 Обязательный. Имя, указывающее, какое приложение инструкции обработки. Не может начинаться с «xml» или «XML».  
  
 `piData`  
 Необязательный параметр. Строка, указывающая, каким образом приложение мишенью `piName` должен обрабатывать XML-документа.  
  
 `?>`  
 Обязательный. Обозначает конец инструкции обработки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Примечания  
 Литералы инструкции обработки XML указывают, как приложения должны обрабатывать XML-документа. Когда приложение загружает XML-документ, приложение может проверять инструкции по обработке XML, чтобы определить способ обработки документа. Приложение интерпретирует значение `piName` и `piData`.  
  
 XML-литерала документа использует синтаксис, который аналогичен инструкции по обработке XML. Дополнительные сведения см. в разделе [литерала документа XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  `piName` Элемент не может начинаться с строки «xml» или «XML», поскольку в спецификации XML 1.0 резервирует эти идентификаторы.  
  
 Можно присвоить переменной литерала инструкции обработки XML или включить в литерал XML-документа.  
  
> [!NOTE]
>  XML-литерал может занимать несколько строк без необходимости символы продолжения строки. Это позволяет скопировать содержимое из XML-документа и вставьте его непосредственно в программу Visual Basic.  
  
 Компилятор Visual Basic литерала инструкции обработки XML преобразуется в вызов <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> конструктор.  
  
## <a name="example"></a>Пример  
 В следующем примере создается инструкция по обработке, определяющая таблицу стилей для XML-документа.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XProcessingInstruction>
- [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
