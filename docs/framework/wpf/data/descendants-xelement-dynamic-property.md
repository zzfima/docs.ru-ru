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
# <a name="descendants-xelement-dynamic-property"></a><span data-ttu-id="27992-102">Descendants (динамическое свойство XElement)</span><span class="sxs-lookup"><span data-stu-id="27992-102">Descendants (XElement dynamic property)</span></span>

<span data-ttu-id="27992-103">Возвращает индексатор, который используется для получения всех элементов-потомков текущего элемента, соответствующих заданному развернутому имени.</span><span class="sxs-lookup"><span data-stu-id="27992-103">Gets an indexer used to retrieve all the descendant elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="27992-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27992-104">Syntax</span></span>

```xaml
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="27992-105">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27992-105">Property value/return value</span></span>

<span data-ttu-id="27992-106">Индексатор типа `IEnumerable<XElement> Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="27992-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="27992-107">Этот индексатор принимает развернутое имя указанных элементов-потомков и возвращает соответствующие дочерние элементы в коллекции <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.</span><span class="sxs-lookup"><span data-stu-id="27992-107">This indexer takes the expanded name of the specified descendant elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="27992-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="27992-108">Remarks</span></span>

<span data-ttu-id="27992-109">Это свойство эквивалентно методу <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> класса <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="27992-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="27992-110">Элементы в возвращаемой коллекции располагаются в порядке исходного XML-документа.</span><span class="sxs-lookup"><span data-stu-id="27992-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="27992-111">В данном свойстве используется отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="27992-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="27992-112">См. также</span><span class="sxs-lookup"><span data-stu-id="27992-112">See also</span></span>

- [<span data-ttu-id="27992-113">Динамические свойства класса XElement</span><span class="sxs-lookup"><span data-stu-id="27992-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- <span data-ttu-id="27992-114">[Elements (XElement Dynamic Property)](elements-xelement-dynamic-property.md) (Elements (Динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="27992-114">[Elements](elements-xelement-dynamic-property.md)</span></span>
