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
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a>Инструкции. Получение сведений о типах и членах с помощью отражения
Пространство имен <xref:System.Reflection> содержит много методов для получения сведений о типах и их членах. В этой статье демонстрируется один из этих методов — <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>. Дополнительные сведения см. в разделе [Общие сведения об отражении](reflection.md).
  
## <a name="example"></a>Пример

В следующем примере демонстрируется получение сведений о типах и членах с помощью отражения:

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a>См. также

- [Программирование с использованием доменов приложений](../app-domains/application-domains.md#programming-with-application-domains)
- [Отражение](reflection.md)
- [Использование доменов приложений](../app-domains/use.md)
