---
title: Attribute (динамическое свойство XElement)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 2b645575a5b6876ffbb52a999c4e05a2de037493
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921206"
---
# <a name="attribute-xelement-dynamic-property"></a>Attribute (динамическое свойство XElement)

Возвращает индексатор, используемый для получения экземпляра атрибута, соответствующего указанному развернутому имени.

## <a name="syntax"></a>Синтаксис

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение

Индексатор типа `XAttribute Item(String expandedName)`. Данный индексатор принимает развернутое имя указанного атрибута и возвращает соответствующий <xref:System.Xml.Linq.XAttribute> или значение `null`, если не существует атрибута с указанным именем.

## <a name="remarks"></a>Заметки

Это свойство эквивалентно методу <xref:System.Xml.Linq.XElement.Attribute%2A> класса <xref:System.Xml.Linq.XElement?displayProperty=fullName>.

## <a name="see-also"></a>См. также

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [Динамические свойства класса XElement](attribute-xelement-dynamic-property.md)
- [Значение](value-xattribute-dynamic-property.md)
