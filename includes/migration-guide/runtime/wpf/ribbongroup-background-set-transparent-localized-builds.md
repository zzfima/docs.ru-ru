---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59236092"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="3376f-101">В локализованных сборках для RibbonGroup устанавливается прозрачный фон</span><span class="sxs-lookup"><span data-stu-id="3376f-101">RibbonGroup background is set to transparent in localized builds</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3376f-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3376f-102">Details</span></span>|<span data-ttu-id="3376f-103">Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3376f-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="3376f-104">Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, благодаря чему гарантируется выбор правильной кисти.</span><span class="sxs-lookup"><span data-stu-id="3376f-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, which in turn ensures that the correct brush is selected.</span></span>|
|<span data-ttu-id="3376f-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="3376f-105">Suggestion</span></span>|<span data-ttu-id="3376f-106">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="3376f-106">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="3376f-107">Область</span><span class="sxs-lookup"><span data-stu-id="3376f-107">Scope</span></span>|<span data-ttu-id="3376f-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="3376f-108">Edge</span></span>|
|<span data-ttu-id="3376f-109">Версия</span><span class="sxs-lookup"><span data-stu-id="3376f-109">Version</span></span>|<span data-ttu-id="3376f-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="3376f-110">4.6.2</span></span>|
|<span data-ttu-id="3376f-111">Тип</span><span class="sxs-lookup"><span data-stu-id="3376f-111">Type</span></span>|<span data-ttu-id="3376f-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="3376f-112">Runtime</span></span>|
