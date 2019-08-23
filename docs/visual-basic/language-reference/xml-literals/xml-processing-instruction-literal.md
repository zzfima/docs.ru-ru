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
ms.openlocfilehash: c589d3f4ac6bbb9aa9b2b8f2535888bddbf9c934
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958483"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Литерал инструкции обработки XML (Visual Basic)
Литерал, представляющий <xref:System.Xml.Linq.XProcessingInstruction> объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Части  
 `<?`  
 Обязательный. Обозначает начало литерала инструкции обработки XML.  
  
 `piName`  
 Обязательный. Имя, указывающее, какое приложение предназначено для инструкции по обработке. Не может начинаться с "XML" или "XML".  
  
 `piData`  
 Необязательный параметр. Строка, указывающая, как целевое `piName` приложение должно обрабатывать XML-документ.  
  
 `?>`  
 Обязательный. Обозначает конец инструкции по обработке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Примечания  
 Литералы инструкций обработки XML указывают, как приложения должны обрабатывать XML-документ. Когда приложение загружает XML-документ, приложение может проверить инструкции по обработке XML, чтобы определить способ обработки документа. Приложение интерпретирует значение `piName` и `piData`.  
  
 В литерале XML-документа используется синтаксис, схожий с инструкцией по обработке XML. Дополнительные сведения см. в разделе [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
> `piName` Элемент не может начинаться со строк "XML" или "XML", поскольку спецификация XML 1,0 резервирует эти идентификаторы.  
  
 Литерал инструкции обработки XML можно назначить переменной или включить в литерал XML-документа.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк без символов продолжения строки. Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал инструкции обработки XML в вызов <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> конструктора.  
  
## <a name="example"></a>Пример  
 В следующем примере создается инструкция по обработке, определяющая таблицу стилей для XML-документа.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XProcessingInstruction>
- [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
