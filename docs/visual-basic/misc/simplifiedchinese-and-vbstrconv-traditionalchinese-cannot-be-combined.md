---
title: VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: 06fa5efdc36dd4501192838394b9bc63b1b959c5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648876"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a><span data-ttu-id="67322-102">VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе</span><span class="sxs-lookup"><span data-stu-id="67322-102">SimplifiedChinese and VbStrConv.TraditionalChinese cannot be combined</span></span>
<span data-ttu-id="67322-103">Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `SimplifiedChinese` , являющиеся членами перечисления `TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="67322-103">Your application is attempting to combine the `VbStrConv` enumeration members `SimplifiedChinese` and `TraditionalChinese`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="67322-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="67322-104">To correct this error</span></span>  
  
- <span data-ttu-id="67322-105">Удалите `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="67322-105">Remove either `VbStrConv.SimplifiedChinese` or `VbStrConv.TraditionalChinese`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67322-106">См. также</span><span class="sxs-lookup"><span data-stu-id="67322-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="67322-107">Знакомство с международными приложениями на платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="67322-107">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
