---
title: "Свойство-индексатор расширения (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
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
ms.openlocfilehash: 25f434a5b5f8caf013ad5f778897e4e98e3d825d
ms.lasthandoff: 03/13/2017

---
# <a name="extension-indexer-property-visual-basic"></a>Свойство-индексатор расширения (Visual Basic)
Обеспечивает доступ к отдельным элементам коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
object(index)  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`object`|Обязательный. Запрашиваемой коллекции. То есть, коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>|  
|(|Обязательный. Обозначает начало свойства индексатора.|  
|`index`|Обязательный. Целочисленное выражение, задающее позицию (с нуля) элемента коллекции.|  
|)|Обязательный. Обозначает конец свойства индексатора.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект из указанного расположения в коллекции, или `Nothing` Если индекс вне допустимого диапазона.  
  
## <a name="remarks"></a>Примечания  
 Свойство-индексатор расширения можно использовать для доступа к отдельным элементам в коллекции. Это свойство индексатора обычно используется на выходе свойства оси XML. Дочерние XML и XML descendant axis свойства возвращают коллекции <xref:System.Xml.Linq.XElement>объектов или значение атрибута.</xref:System.Xml.Linq.XElement>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует свойства индексатора расширения вызовы`ElementAtOrDefault` метод. В отличие от индексатора массива`ElementAtOrDefault` возвращает `Nothing` , если индекс выходит за пределы диапазона. Это полезно в тех случаях, когда не удается легко определить число элементов в коллекции.  
  
 Это свойство индексатора доступно как свойство расширения для коллекций, реализующих <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Linq.IQueryable%601>: он используется только в том случае, если коллекция не имеет индексатора или свойство по умолчанию.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Для доступа к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>объектов, которые можно использовать XML `Value` свойства.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует использование индексатора расширения для доступа к второй дочерний узел в коллекцию <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> Эта коллекция доступна с помощью свойства дочерней оси, который получает все дочерние элементы с именем `phone` в `contact` объекта.  
  
 [!code-vb[VbXMLSamples&#24;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
