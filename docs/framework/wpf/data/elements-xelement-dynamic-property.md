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
# <a name="elements-xelement-dynamic-property"></a><span data-ttu-id="3b93e-102">Elements (динамическое свойство XElement)</span><span class="sxs-lookup"><span data-stu-id="3b93e-102">Elements (XElement dynamic property)</span></span>

<span data-ttu-id="3b93e-103">Получает индексатор, который используется для извлечения дочернего элемента текущего элемента с заданным развернутым именем.</span><span class="sxs-lookup"><span data-stu-id="3b93e-103">Gets an indexer used to retrieve the child elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b93e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b93e-104">Syntax</span></span>

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="3b93e-105">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b93e-105">Property value/return value</span></span>

<span data-ttu-id="3b93e-106">Индексатор типа `IEnumerable<XElement> Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="3b93e-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="3b93e-107">Индексатор принимает развернутое имя нужных дочерних элементов и возвращает соответствующие дочерние элементы в коллекцию <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.</span><span class="sxs-lookup"><span data-stu-id="3b93e-107">This indexer takes the expanded name of the desired child elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b93e-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="3b93e-108">Remarks</span></span>

<span data-ttu-id="3b93e-109">Это свойство эквивалентно методу <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> класса <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="3b93e-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="3b93e-110">Элементы в возвращаемой коллекции располагаются в порядке исходного XML-документа.</span><span class="sxs-lookup"><span data-stu-id="3b93e-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="3b93e-111">В данном свойстве используется отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="3b93e-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b93e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3b93e-112">See also</span></span>

- [<span data-ttu-id="3b93e-113">Динамические свойства класса XElement</span><span class="sxs-lookup"><span data-stu-id="3b93e-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="3b93e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="3b93e-114">Element</span></span>](element-xelement-dynamic-property.md)
- [<span data-ttu-id="3b93e-115">Descendants (динамическое свойство XElement)</span><span class="sxs-lookup"><span data-stu-id="3b93e-115">Descendants</span></span>](descendants-xelement-dynamic-property.md)
