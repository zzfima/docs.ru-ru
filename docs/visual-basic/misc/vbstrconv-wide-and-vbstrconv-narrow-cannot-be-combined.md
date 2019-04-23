---
title: VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 917fcdfcb34778074db6a19c04e12c3cf8de90dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307929"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Globalization>

- [Знакомство с международными приложениями на платформе .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
