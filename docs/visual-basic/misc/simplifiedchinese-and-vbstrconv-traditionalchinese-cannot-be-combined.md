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
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a><span data-ttu-id="bd5e6-102">VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе</span><span class="sxs-lookup"><span data-stu-id="bd5e6-102">SimplifiedChinese and VbStrConv.TraditionalChinese cannot be combined</span></span>
<span data-ttu-id="bd5e6-103">Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `SimplifiedChinese` , являющиеся членами перечисления `TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="bd5e6-103">Your application is attempting to combine the `VbStrConv` enumeration members `SimplifiedChinese` and `TraditionalChinese`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bd5e6-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bd5e6-104">To correct this error</span></span>  
  
- <span data-ttu-id="bd5e6-105">Удалите `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="bd5e6-105">Remove either `VbStrConv.SimplifiedChinese` or `VbStrConv.TraditionalChinese`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5e6-106">См. также</span><span class="sxs-lookup"><span data-stu-id="bd5e6-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="bd5e6-107">Разработка глобализованных и локализованных приложений</span><span class="sxs-lookup"><span data-stu-id="bd5e6-107">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
