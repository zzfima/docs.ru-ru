---
title: Практическое руководство. Доступа к дочерним XML-элементам (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: cd1b0db5305c7879d89cfdfff6cd458d6dea14f4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836822"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Практическое руководство. Доступа к дочерним XML-элементам (Visual Basic)
В этом примере показано, как использовать дочернего свойства оси для доступа к все дочерние элементы XML, которые имеют указанное имя элемента XML. В частности, он использует <xref:System.Xml.Linq.XElement.Value%2A> свойство, чтобы получить значение первого элемента в коллекции, `name` возвращает свойство дочерней оси. `name` Child axis-свойство получает все дочерние элементы с именем `phone` в `contact` объекта. В этом примере также используется `phone` свойство дочерней оси для доступа к все дочерние элементы с именем `phone` , содержащихся в `contact` объекта.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылка на пространство имен <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Свойство значения XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
