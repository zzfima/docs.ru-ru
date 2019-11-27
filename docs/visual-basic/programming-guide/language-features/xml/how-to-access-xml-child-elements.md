---
title: Практическое руководство. Доступ к дочерним XML-элементам
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: af5ea809cb0777b16230f20e133764dd5f1f86d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332341"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Практическое руководство. Доступ к дочерним XML-элементам (Visual Basic)
В этом примере показано, как использовать свойство дочерней оси для доступа ко всем дочерним элементам XML с указанным именем в элементе XML. В частности, для получения значения первого элемента в коллекции, возвращаемого свойством дочерней оси `name`, используется свойство <xref:System.Xml.Linq.XElement.Value%2A>. Свойство дочерней оси `name` получает все дочерние элементы с именами `phone` в объекте `contact`. В этом примере также используется свойство дочерней оси `phone` для доступа ко всем дочерним элементам с именем `phone`, содержащимся в объекте `contact`.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылка на пространство имен <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Свойство значения XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
