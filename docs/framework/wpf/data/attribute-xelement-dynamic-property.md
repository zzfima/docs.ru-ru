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
# <a name="attribute-xelement-dynamic-property"></a><span data-ttu-id="e88e1-102">Attribute (динамическое свойство XElement)</span><span class="sxs-lookup"><span data-stu-id="e88e1-102">Attribute (XElement dynamic property)</span></span>

<span data-ttu-id="e88e1-103">Возвращает индексатор, используемый для получения экземпляра атрибута, соответствующего указанному развернутому имени.</span><span class="sxs-lookup"><span data-stu-id="e88e1-103">Gets an indexer used to retrieve the attribute instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="e88e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e88e1-104">Syntax</span></span>

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="e88e1-105">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e88e1-105">Property value/return value</span></span>

<span data-ttu-id="e88e1-106">Индексатор типа `XAttribute Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="e88e1-106">An indexer of the type `XAttribute Item(String expandedName)`.</span></span> <span data-ttu-id="e88e1-107">Данный индексатор принимает развернутое имя указанного атрибута и возвращает соответствующий <xref:System.Xml.Linq.XAttribute> или значение `null`, если не существует атрибута с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="e88e1-107">This indexer takes the expanded name of the specified attribute and returns the corresponding <xref:System.Xml.Linq.XAttribute>, or `null` if there is no attribute with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="e88e1-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e88e1-108">Remarks</span></span>

<span data-ttu-id="e88e1-109">Это свойство эквивалентно методу <xref:System.Xml.Linq.XElement.Attribute%2A> класса <xref:System.Xml.Linq.XElement?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e88e1-109">This property is equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="e88e1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e88e1-110">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [<span data-ttu-id="e88e1-111">Динамические свойства класса XElement</span><span class="sxs-lookup"><span data-stu-id="e88e1-111">XElement Class Dynamic Properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="e88e1-112">Значение</span><span class="sxs-lookup"><span data-stu-id="e88e1-112">Value</span></span>](value-xattribute-dynamic-property.md)
