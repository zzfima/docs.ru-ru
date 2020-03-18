---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802492"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="db605-101">В локализованных сборках для RibbonGroup устанавливается прозрачный фон</span><span class="sxs-lookup"><span data-stu-id="db605-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="db605-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="db605-102">Details</span></span>|<span data-ttu-id="db605-103">Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="db605-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="db605-104">Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, благодаря чему гарантируется выбор правильной кисти.</span><span class="sxs-lookup"><span data-stu-id="db605-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="db605-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="db605-105">Suggestion</span></span>|<span data-ttu-id="db605-106">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="db605-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="db605-107">Область</span><span class="sxs-lookup"><span data-stu-id="db605-107">Scope</span></span>|<span data-ttu-id="db605-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="db605-108">Edge</span></span>|
|<span data-ttu-id="db605-109">Version</span><span class="sxs-lookup"><span data-stu-id="db605-109">Version</span></span>|<span data-ttu-id="db605-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="db605-110">4.6.2</span></span>|
|<span data-ttu-id="db605-111">Type</span><span class="sxs-lookup"><span data-stu-id="db605-111">Type</span></span>|<span data-ttu-id="db605-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="db605-112">Runtime</span></span>|
