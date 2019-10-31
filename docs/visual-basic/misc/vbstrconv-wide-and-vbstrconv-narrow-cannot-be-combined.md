---
title: VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: e90af8ba91872a04be11524753d9df0d168315ca
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198241"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Globalization>

- [Разработка глобализованных и локализованных приложений](/visualstudio/ide/globalizing-and-localizing-applications)
