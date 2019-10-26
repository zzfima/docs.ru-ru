---
title: Elements (динамическое свойство XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.openlocfilehash: 812adabd3bfb01fd9313ce3f35e6cb0a5e23344e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921152"
---
# <a name="elements-xelement-dynamic-property"></a>Elements (динамическое свойство XElement)

Получает индексатор, который используется для извлечения дочернего элемента текущего элемента с заданным развернутым именем.

## <a name="syntax"></a>Синтаксис

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Индексатор типа `IEnumerable<XElement> Item(String expandedName)`. Индексатор принимает развернутое имя нужных дочерних элементов и возвращает соответствующие дочерние элементы в коллекцию <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.

## <a name="remarks"></a>Заметки

Это свойство эквивалентно методу <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> класса <xref:System.Xml.Linq.XContainer>.

Элементы в возвращаемой коллекции располагаются в порядке исходного XML-документа.

В данном свойстве используется отложенное выполнение.

## <a name="see-also"></a>См. также

- [Динамические свойства класса XElement](attribute-xelement-dynamic-property.md)
- [Элемент](element-xelement-dynamic-property.md)
- [Descendants (динамическое свойство XElement)](descendants-xelement-dynamic-property.md)
