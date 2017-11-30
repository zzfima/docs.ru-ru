---
title: "VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb42ffd72a7e1f9bceabc8e8b67310b4ca2ab716
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="7a434-102">VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе</span><span class="sxs-lookup"><span data-stu-id="7a434-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>
<span data-ttu-id="7a434-103">Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.</span><span class="sxs-lookup"><span data-stu-id="7a434-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a434-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7a434-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="7a434-105">Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.</span><span class="sxs-lookup"><span data-stu-id="7a434-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a434-106">См. также</span><span class="sxs-lookup"><span data-stu-id="7a434-106">See Also</span></span>  
 <xref:System.Globalization>  
 [<span data-ttu-id="7a434-107">НЕ В СБОРКЕ. Перечисление VbStrConv</span><span class="sxs-lookup"><span data-stu-id="7a434-107">NOTINBUILD VbStrConv Enumeration</span></span>](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936)  
 [<span data-ttu-id="7a434-108">Знакомство с международными приложениями на платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a434-108">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
