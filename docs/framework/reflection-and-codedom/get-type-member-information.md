---
title: Инструкции. Получение сведений о типах и членах с помощью отражения
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: 9ffc173bbd0ed12eedea0c191f6d39baf181793a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130205"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="ce423-102">Инструкции. Получение сведений о типах и членах с помощью отражения</span><span class="sxs-lookup"><span data-stu-id="ce423-102">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="ce423-103">Пространство имен <xref:System.Reflection> содержит много методов для получения сведений о типах и их членах.</span><span class="sxs-lookup"><span data-stu-id="ce423-103">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="ce423-104">В этой статье демонстрируется один из этих методов — <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce423-104">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ce423-105">Дополнительные сведения см. в разделе [Общие сведения об отражении](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="ce423-105">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="ce423-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ce423-106">Example</span></span>

<span data-ttu-id="ce423-107">В следующем примере демонстрируется получение сведений о типах и членах с помощью отражения:</span><span class="sxs-lookup"><span data-stu-id="ce423-107">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="ce423-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ce423-108">See also</span></span>

- [<span data-ttu-id="ce423-109">Программирование с использованием доменов приложений</span><span class="sxs-lookup"><span data-stu-id="ce423-109">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="ce423-110">Отражение</span><span class="sxs-lookup"><span data-stu-id="ce423-110">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="ce423-111">Использование доменов приложений</span><span class="sxs-lookup"><span data-stu-id="ce423-111">Use application domains</span></span>](../app-domains/use.md)
