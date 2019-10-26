---
title: Element (динамическое свойство XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.openlocfilehash: fc0277d0dc38574696f01e6915e5382744345771
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921188"
---
# <a name="element-xelement-dynamic-property"></a><span data-ttu-id="aa8c5-102">Element (динамическое свойство XElement)</span><span class="sxs-lookup"><span data-stu-id="aa8c5-102">Element (XElement dynamic property)</span></span>

<span data-ttu-id="aa8c5-103">Получает индексатор, который используется для получения экземпляра дочернего элемента, соответствующего указанному развернутому имени.</span><span class="sxs-lookup"><span data-stu-id="aa8c5-103">Gets an indexer used to retrieve the child element instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa8c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa8c5-104">Syntax</span></span>

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="aa8c5-105">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aa8c5-105">Property value/return value</span></span>

<span data-ttu-id="aa8c5-106">Индексатор типа `XElement Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="aa8c5-106">An indexer of the type `XElement Item(String expandedName)`.</span></span> <span data-ttu-id="aa8c5-107">Этот индексатор берет параметр развернутого имени и возвращает соответствующее значение элемента <xref:System.Xml.Linq.XElement> или `null`, если элемента с таким именем не существует.</span><span class="sxs-lookup"><span data-stu-id="aa8c5-107">This indexer takes an expanded name parameter and returns the corresponding <xref:System.Xml.Linq.XElement>, or `null` if there is no element with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa8c5-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="aa8c5-108">Remarks</span></span>

<span data-ttu-id="aa8c5-109">Это свойство эквивалентно методу <xref:System.Xml.Linq.XContainer.Element%2A> класса <xref:System.Xml.Linq.XContainer?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="aa8c5-109">This property is equivalent to <xref:System.Xml.Linq.XContainer.Element%2A> method of the <xref:System.Xml.Linq.XContainer?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa8c5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="aa8c5-110">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [<span data-ttu-id="aa8c5-111">Динамические свойства класса XElement</span><span class="sxs-lookup"><span data-stu-id="aa8c5-111">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- <span data-ttu-id="aa8c5-112">[Elements (XElement Dynamic Property)](elements-xelement-dynamic-property.md) (Elements (Динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="aa8c5-112">[Elements](elements-xelement-dynamic-property.md)</span></span>
