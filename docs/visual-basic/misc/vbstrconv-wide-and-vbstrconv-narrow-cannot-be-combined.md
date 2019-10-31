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
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="9cb5a-102">VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе</span><span class="sxs-lookup"><span data-stu-id="9cb5a-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>
<span data-ttu-id="9cb5a-103">Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.</span><span class="sxs-lookup"><span data-stu-id="9cb5a-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9cb5a-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9cb5a-104">To correct this error</span></span>  
  
1. <span data-ttu-id="9cb5a-105">Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.</span><span class="sxs-lookup"><span data-stu-id="9cb5a-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb5a-106">См. также</span><span class="sxs-lookup"><span data-stu-id="9cb5a-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="9cb5a-107">Разработка глобализованных и локализованных приложений</span><span class="sxs-lookup"><span data-stu-id="9cb5a-107">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
