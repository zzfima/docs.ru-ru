---
title: "VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0fd6006fd346b0fe43958bfb6806759a3bcfb0f1
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a><span data-ttu-id="1018d-102">VbStrConv.SimplifiedChinese и VbStrConv.TraditionalChinese не могут использоваться вместе</span><span class="sxs-lookup"><span data-stu-id="1018d-102">SimplifiedChinese and VbStrConv.TraditionalChinese cannot be combined</span></span>
<span data-ttu-id="1018d-103">Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `SimplifiedChinese` , являющиеся членами перечисления `TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="1018d-103">Your application is attempting to combine the `VbStrConv` enumeration members `SimplifiedChinese` and `TraditionalChinese`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1018d-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1018d-104">To correct this error</span></span>  
  
-   <span data-ttu-id="1018d-105">Удалите `VbStrConv.SimplifiedChinese` или `VbStrConv.TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="1018d-105">Remove either `VbStrConv.SimplifiedChinese` or `VbStrConv.TraditionalChinese`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1018d-106">См. также</span><span class="sxs-lookup"><span data-stu-id="1018d-106">See Also</span></span>  
 <xref:System.Globalization>  
   
 [<span data-ttu-id="1018d-107">Знакомство с международными приложениями на платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1018d-107">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
