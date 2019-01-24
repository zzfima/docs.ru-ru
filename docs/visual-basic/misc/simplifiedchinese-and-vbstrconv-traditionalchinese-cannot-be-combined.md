---
title: VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: 0d07b419f11692d080000ee689d545054ddfd92c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549585"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a><span data-ttu-id="9510a-102">VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе</span><span class="sxs-lookup"><span data-stu-id="9510a-102">SimplifiedChinese and VbStrConv.TraditionalChinese cannot be combined</span></span>
<span data-ttu-id="9510a-103">Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `SimplifiedChinese` , являющиеся членами перечисления `TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="9510a-103">Your application is attempting to combine the `VbStrConv` enumeration members `SimplifiedChinese` and `TraditionalChinese`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9510a-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9510a-104">To correct this error</span></span>  
  
-   <span data-ttu-id="9510a-105">Удалите `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="9510a-105">Remove either `VbStrConv.SimplifiedChinese` or `VbStrConv.TraditionalChinese`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9510a-106">См. также</span><span class="sxs-lookup"><span data-stu-id="9510a-106">See also</span></span>
- <xref:System.Globalization>

- [<span data-ttu-id="9510a-107">Знакомство с международными приложениями на платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9510a-107">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
