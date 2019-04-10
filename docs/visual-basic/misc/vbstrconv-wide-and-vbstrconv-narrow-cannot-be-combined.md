---
title: VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 917fcdfcb34778074db6a19c04e12c3cf8de90dc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307929"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="c76ed-102">VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе</span><span class="sxs-lookup"><span data-stu-id="c76ed-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>
<span data-ttu-id="c76ed-103">Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.</span><span class="sxs-lookup"><span data-stu-id="c76ed-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c76ed-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c76ed-104">To correct this error</span></span>  
  
1. <span data-ttu-id="c76ed-105">Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.</span><span class="sxs-lookup"><span data-stu-id="c76ed-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76ed-106">См. также</span><span class="sxs-lookup"><span data-stu-id="c76ed-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="c76ed-107">Знакомство с международными приложениями на платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c76ed-107">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
