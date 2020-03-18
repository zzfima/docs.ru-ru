---
title: Устранение рисков. Отрисовка окна WPF
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
ms.openlocfilehash: 42d6abf1ba6ed7c17a5a5604e98b5ee46d0c3ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457764"
---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="6c603-102">Устранение рисков. Отрисовка окна WPF</span><span class="sxs-lookup"><span data-stu-id="6c603-102">Mitigation: WPF Window Rendering</span></span>

<span data-ttu-id="6c603-103">В .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов.</span><span class="sxs-lookup"><span data-stu-id="6c603-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>

## <a name="impact"></a><span data-ttu-id="6c603-104">Последствия</span><span class="sxs-lookup"><span data-stu-id="6c603-104">Impact</span></span>

<span data-ttu-id="6c603-105">Как правило, отображение всего окна на нескольких мониторах без усечения является ожидаемым поведением.</span><span class="sxs-lookup"><span data-stu-id="6c603-105">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="6c603-106">Тем не менее, в Windows 7 и более ранних версий окна WPF обрезаются в случае выхода за пределы одного экрана, так как отрисовка части окна на втором мониторе значительно снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="6c603-106">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>

<span data-ttu-id="6c603-107">Из-за влияния большого числа факторов невозможно указать точные сведения о том, как отображение окон WPF на нескольких мониторах в Windows 8 и более поздних версий воздействует на производительность.</span><span class="sxs-lookup"><span data-stu-id="6c603-107">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="6c603-108">В некоторых случаях это по-прежнему может оказывать нежелательное влияние на производительность, особенно для пользователей, запускающих приложения, которые обрабатывают большие объемы графических данных, с разнесением окон на несколько мониторов.</span><span class="sxs-lookup"><span data-stu-id="6c603-108">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="6c603-109">В других случаях может просто требоваться согласованное поведение разных версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6c603-109">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>

## <a name="mitigation"></a><span data-ttu-id="6c603-110">Меры по снижению риска</span><span class="sxs-lookup"><span data-stu-id="6c603-110">Mitigation</span></span>

<span data-ttu-id="6c603-111">Можно отключить это изменение и вернуться к предыдущему поведению обрезки окна WPF, когда оно выходит за пределы одного экрана.</span><span class="sxs-lookup"><span data-stu-id="6c603-111">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="6c603-112">Это можно осуществить двумя путями:</span><span class="sxs-lookup"><span data-stu-id="6c603-112">There are two ways to do this:</span></span>

- <span data-ttu-id="6c603-113">Добавив элемент `<EnableMultiMonitorDisplayClipping>` в раздел `<appSettings>` файла конфигурации приложения, можно включить или отключить это поведение для приложений, выполняющихся в Windows 8 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="6c603-113">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="6c603-114">Например, следующий раздел конфигурации отключает отрисовку без обрезки.</span><span class="sxs-lookup"><span data-stu-id="6c603-114">For example, the following configuration section disables rendering without clipping:</span></span>

  ```xml
  <appSettings>
      <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    </appSettings>
  ```

  <span data-ttu-id="6c603-115">Параметр конфигурации `<EnableMultiMonitorDisplayClipping>` может иметь одно из двух значений:</span><span class="sxs-lookup"><span data-stu-id="6c603-115">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>

  - <span data-ttu-id="6c603-116">`true` — для включения обрезки окон по границам монитора во время отрисовки;</span><span class="sxs-lookup"><span data-stu-id="6c603-116">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>

  - <span data-ttu-id="6c603-117">`false` — для отключения обрезки окон по границам монитора во время отрисовки.</span><span class="sxs-lookup"><span data-stu-id="6c603-117">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>

- <span data-ttu-id="6c603-118">Путем задания значения <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> для свойства `true` при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="6c603-118">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c603-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6c603-119">See also</span></span>

- [<span data-ttu-id="6c603-120">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="6c603-120">Application compatibility</span></span>](application-compatibility.md)
