---
title: Свойство-индексатор расширения (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6bcb19388a9449a76eed5689b12fb95c5a4fb8de
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
|`object`|Обязательно. Запрашиваемой коллекции. То есть, коллекция, реализующая <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>.|  
|(|Обязательно. Обозначает начало свойства индексатора.|  
|`index`|Обязательно. Целочисленное выражение, задающее позицию (с нуля) элемента коллекции.|  
|)|Обязательно. Обозначает конец свойства индексатора.|  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект из указанного расположения в коллекции, или `Nothing` Если индекс вне допустимого диапазона.  
  
## <a name="remarks"></a>Примечания  
 Свойство-индексатор расширения можно использовать для доступа к отдельным элементам в коллекции. Это свойство индексатора обычно используется на выходе свойства оси XML. Дочерние XML и свойства XML descendant axis возвращают коллекции <xref:System.Xml.Linq.XElement> объектов или значение атрибута.  
  
 Компилятор Visual Basic преобразует свойства индексатора расширения вызовы `ElementAtOrDefault` метод. В отличие от индексатора массива `ElementAtOrDefault` возвращает `Nothing` Если индекс вне допустимого диапазона. Это полезно в тех случаях, когда не удается легко определить число элементов в коллекции.  
  
 Это свойство индексатора доступно как свойство расширения для коллекций, реализующих <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>: оно используется только в том случае, если коллекция не имеет индексатора или свойства по умолчанию.  
  
 Для доступа к значению первого элемента в коллекции <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> объектов, которые можно использовать XML `Value` свойства. Дополнительные сведения см. в разделе [свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как использовать индексатор расширения для доступа к второй дочерний узел в коллекцию <xref:System.Xml.Linq.XElement> объектов. Доступ к коллекции с помощью свойства дочерней оси, который получает все дочерние элементы с именем `phone` в `contact` объекта.  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Этот пример кода отображает следующий текст:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XElement>  
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML-литералы](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Свойство значения XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
