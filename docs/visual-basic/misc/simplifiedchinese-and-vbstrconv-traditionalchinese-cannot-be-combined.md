---
title: VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: b3c75e64624d6be6df2db216a0ad336c9ef583a7
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197218"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `SimplifiedChinese` , являющиеся членами перечисления `TraditionalChinese`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Globalization>

- [Разработка глобализованных и локализованных приложений](/visualstudio/ide/globalizing-and-localizing-applications)
