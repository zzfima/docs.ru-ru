---
title: Устранение рисков. Макет WPF
ms.date: 03/30/2017
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
ms.openlocfilehash: 7a074698fd203d0c5f9b799bfee8a6a9cb40800e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457785"
---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="7d05a-102">Устранение рисков. Макет WPF</span><span class="sxs-lookup"><span data-stu-id="7d05a-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="7d05a-103">Макет элементов управления WPF может немного изменяться.</span><span class="sxs-lookup"><span data-stu-id="7d05a-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="7d05a-104">Последствия</span><span class="sxs-lookup"><span data-stu-id="7d05a-104">Impact</span></span>  
 <span data-ttu-id="7d05a-105">В результате этого изменения:</span><span class="sxs-lookup"><span data-stu-id="7d05a-105">As a result of this change:</span></span>  
  
- <span data-ttu-id="7d05a-106">ширина или высота элементов может увеличиться или уменьшиться максимум на один пиксель;</span><span class="sxs-lookup"><span data-stu-id="7d05a-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
- <span data-ttu-id="7d05a-107">расположение объекта может измениться максимум на один пиксель;</span><span class="sxs-lookup"><span data-stu-id="7d05a-107">The placement of an object can move by at most one pixel.</span></span>  
  
- <span data-ttu-id="7d05a-108">выровненные по центру элементы могут сместиться по вертикали или горизонтали максимум на один пиксель.</span><span class="sxs-lookup"><span data-stu-id="7d05a-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="7d05a-109">По умолчанию новый макет включен только для приложений, предназначенных для .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="7d05a-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="7d05a-110">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="7d05a-110">Mitigation</span></span>  
 <span data-ttu-id="7d05a-111">Поскольку это изменение, как правило, приводит к устранению обрезки правых или нижних элементов управления WPF при высоком разрешении, для приложений, предназначенных для более ранних версий .NET Framework, но выполняющихся в .NET Framework 4.6, можно выбрать это новое поведение, добавив следующую строку в раздел `<runtime>` файла app.config.</span><span class="sxs-lookup"><span data-stu-id="7d05a-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="7d05a-112">Для приложений, предназначенных для .NET Framework 4.6, для которых требуется задать отрисовку элементов управления WPF с помощью прежнего алгоритма макета, можно добавить следующую строку в раздел `<runtime>` файла app.config.</span><span class="sxs-lookup"><span data-stu-id="7d05a-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d05a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7d05a-113">See also</span></span>

- [<span data-ttu-id="7d05a-114">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="7d05a-114">Application compatibility</span></span>](application-compatibility.md)
