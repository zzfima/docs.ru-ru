---
title: Свойство-индексатор расширения
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 5f91dc8a6b1a0d82daa4891cf826c16e2716839f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352701"
---
# <a name="extension-indexer-property-visual-basic"></a>Свойство-индексатор расширения (Visual Basic)
Обеспечивает доступ к отдельным элементам коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`object`|Обязательно. Запрашиваемая коллекция. То есть коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.|  
|(|Обязательно. Обозначает начало свойства индексатора.|  
|`index`|Обязательно. Целочисленное выражение, указывающее Отсчитываемая от нуля координату элемента коллекции.|  
|)|Обязательно. Обозначает конец свойства индексатора.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект из указанного расположения в коллекции или `Nothing`, если индекс выходит за пределы допустимого диапазона.  
  
## <a name="remarks"></a>Примечания  
 Свойство индексатора расширения можно использовать для доступа к отдельным элементам в коллекции. Это свойство индексатора обычно используется в выходных данных свойств оси XML. Свойства дочерней оси XML и XML-потомков возвращают коллекции <xref:System.Xml.Linq.XElement> объектов или значение атрибута.  
  
 Компилятор Visual Basic преобразует свойства индексатора расширения в вызовы метода `ElementAtOrDefault`. В отличие от индексатора массива, метод `ElementAtOrDefault` возвращает `Nothing`, если индекс выходит за пределы диапазона. Такое поведение полезно в тех случаях, когда невозможно легко определить количество элементов в коллекции.  
  
 Это свойство индексатора похоже на свойство расширения для коллекций, реализующих <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>: оно используется только в том случае, если коллекция не имеет индексатора или свойства по умолчанию.  
  
 Чтобы получить доступ к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> объектов, можно использовать свойство `Value` XML. Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать индексатор расширений для доступа ко второму дочернему узлу в коллекции объектов <xref:System.Xml.Linq.XElement>. Доступ к коллекции осуществляется с помощью свойства дочерней оси, которое получает все дочерние элементы с именем `phone` в объекте `contact`.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement>
- [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)
- [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
