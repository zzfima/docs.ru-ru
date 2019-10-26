---
title: Xml (динамическое свойство XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Xml
ms.openlocfilehash: 9bac9797f397a0bea1dda36bf864f88293061893
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921038"
---
# <a name="xml-xelement-dynamic-property"></a><span data-ttu-id="49514-102">Xml (динамическое свойство XElement)</span><span class="sxs-lookup"><span data-stu-id="49514-102">Xml (XElement dynamic property)</span></span>

<span data-ttu-id="49514-103">Возвращает неформатированное XML-содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="49514-103">Gets the unformatted XML content of the element.</span></span>

## <a name="syntax"></a><span data-ttu-id="49514-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49514-104">Syntax</span></span>

```xaml
elem.Xml
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="49514-105">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49514-105">Property value/return value</span></span>

<span data-ttu-id="49514-106">Значение <xref:System.String>, представляющее неформатированное XML-содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="49514-106">A <xref:System.String> that represents the unformatted XML content of the element.</span></span>

## <a name="remarks"></a><span data-ttu-id="49514-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="49514-107">Remarks</span></span>

<span data-ttu-id="49514-108">Это свойство эквивалентно методу <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> класса <xref:System.Xml.Linq.XNode?displayProperty=fullName> с параметром `SaveOptions`, установленным равным <xref:System.Xml.Linq.SaveOptions>.</span><span class="sxs-lookup"><span data-stu-id="49514-108">This property is equivalent to the <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> method of the <xref:System.Xml.Linq.XNode?displayProperty=fullName> class, with the `SaveOptions` parameter set to <xref:System.Xml.Linq.SaveOptions>.</span></span>

## <a name="see-also"></a><span data-ttu-id="49514-109">См. также</span><span class="sxs-lookup"><span data-stu-id="49514-109">See also</span></span>

- [<span data-ttu-id="49514-110">Динамические свойства класса XElement</span><span class="sxs-lookup"><span data-stu-id="49514-110">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="49514-111">Значение</span><span class="sxs-lookup"><span data-stu-id="49514-111">Value</span></span>](value-xelement-dynamic-property.md)
