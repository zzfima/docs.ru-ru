---
title: Практическое руководство. Элементам-потомкам XML доступа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: bfbf849bd296f639f03580346e4a9c52ce000abd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832220"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Практическое руководство. Элементам-потомкам XML доступа (Visual Basic)
В этом примере показано, как использовать свойства дочерней оси для доступа ко всем элементам XML с указанным именем, содержащиеся в XML-элемента. В частности, он использует `Value` свойство, чтобы получить значение первого элемента в коллекции, `name` возвращает свойство дочерней оси. `name` Descendant axis-свойство возвращает все элементы с именем `name` , содержащихся в `contacts` объекта. В этом примере также используется `phone` descendant axis-свойство для доступа к всех наследников с именем `phone` , содержащихся в `contacts` объекта.  
  
## <a name="example"></a>Пример  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылка на пространство имен <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [Свойство значения XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Доступ к XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
