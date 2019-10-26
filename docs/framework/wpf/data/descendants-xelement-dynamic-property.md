---
title: Descendants (динамическое свойство XElement)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 8d14b0a94d1a2028a56f649a574f157264ba50fa
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921182"
---
# <a name="descendants-xelement-dynamic-property"></a>Descendants (динамическое свойство XElement)

Возвращает индексатор, который используется для получения всех элементов-потомков текущего элемента, соответствующих заданному развернутому имени.

## <a name="syntax"></a>Синтаксис

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Индексатор типа `IEnumerable<XElement> Item(String expandedName)`. Этот индексатор принимает развернутое имя указанных элементов-потомков и возвращает соответствующие дочерние элементы в коллекции <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.

## <a name="remarks"></a>Заметки

Это свойство эквивалентно методу <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> класса <xref:System.Xml.Linq.XContainer>.

Элементы в возвращаемой коллекции располагаются в порядке исходного XML-документа.

В данном свойстве используется отложенное выполнение.

## <a name="see-also"></a>См. также

- [Динамические свойства класса XElement](attribute-xelement-dynamic-property.md)
- [Elements (XElement Dynamic Property)](elements-xelement-dynamic-property.md) (Elements (Динамическое свойство XElement))
