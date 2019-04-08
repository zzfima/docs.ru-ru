---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760683"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="8855b-101">В локализованных сборках для RibbonGroup устанавливается прозрачный фон</span><span class="sxs-lookup"><span data-stu-id="8855b-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8855b-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8855b-102">Details</span></span>|<span data-ttu-id="8855b-103">Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8855b-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="8855b-104">Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, благодаря чему гарантируется выбор правильной кисти.</span><span class="sxs-lookup"><span data-stu-id="8855b-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="8855b-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="8855b-105">Suggestion</span></span>|<span data-ttu-id="8855b-106">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="8855b-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="8855b-107">Область</span><span class="sxs-lookup"><span data-stu-id="8855b-107">Scope</span></span>|<span data-ttu-id="8855b-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="8855b-108">Edge</span></span>|
|<span data-ttu-id="8855b-109">Версия</span><span class="sxs-lookup"><span data-stu-id="8855b-109">Version</span></span>|<span data-ttu-id="8855b-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="8855b-110">4.6.2</span></span>|
|<span data-ttu-id="8855b-111">Тип</span><span class="sxs-lookup"><span data-stu-id="8855b-111">Type</span></span>|<span data-ttu-id="8855b-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="8855b-112">Runtime</span></span>|

