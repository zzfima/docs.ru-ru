---
title: XML-литерал инструкции обработки
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3602a81feae9287a77d060bb46f10eefee4fc05d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347037"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Литерал инструкции обработки XML (Visual Basic)
Литерал, представляющий объект <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Части  
 `<?`  
 Обязательно. Обозначает начало литерала инструкции обработки XML.  
  
 `piName`  
 Обязательно. Имя, указывающее, какое приложение предназначено для инструкции по обработке. Не может начинаться с "XML" или "XML".  
  
 `piData`  
 Необязательный элемент. Строка, указывающая, как приложение, на которое нацелена `piName`, должно обрабатывать XML-документ.  
  
 `?>`  
 Обязательно. Обозначает конец инструкции по обработке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XProcessingInstruction>.  
  
## <a name="remarks"></a>Примечания  
 Литералы инструкций обработки XML указывают, как приложения должны обрабатывать XML-документ. Когда приложение загружает XML-документ, приложение может проверить инструкции по обработке XML, чтобы определить способ обработки документа. Приложение интерпретирует значение `piName` и `piData`.  
  
 В литерале XML-документа используется синтаксис, схожий с инструкцией по обработке XML. Дополнительные сведения см. в разделе [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
> Элемент `piName` не может начинаться со строк "XML" или "XML", поскольку спецификация XML 1,0 резервирует эти идентификаторы.  
  
 Литерал инструкции обработки XML можно назначить переменной или включить в литерал XML-документа.  
  
> [!NOTE]
> XML-литерал может охватывать несколько строк без символов продолжения строки. Это позволяет копировать содержимое из XML-документа и вставлять его непосредственно в Visual Basic программу.  
  
 Компилятор Visual Basic преобразует литерал инструкции обработки XML в вызов конструктора <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается инструкция по обработке, определяющая таблицу стилей для XML-документа.  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XProcessingInstruction>
- [XML-литерал документа](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
