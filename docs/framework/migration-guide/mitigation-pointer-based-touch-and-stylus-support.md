---
title: Устранение рисков. Устранение рисков. Поддержка сенсорного управления и пера на основе указателя
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
ms.openlocfilehash: 023c38f66611bd0022699d3f62d90c3923585012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "77094479"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a><span data-ttu-id="a08b3-102">Устранение рисков. Устранение рисков. Поддержка сенсорного управления и пера на основе указателя</span><span class="sxs-lookup"><span data-stu-id="a08b3-102">Mitigation: Pointer-based Touch and Stylus Support</span></span>

<span data-ttu-id="a08b3-103">В приложениях WPF, предназначенных для .NET Framework 4.7 и выполняемых в Windows, начиная с версии Windows 10 Creators Update, можно включить дополнительный стек сенсорного управления и пера WPF на основе `WM_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="a08b3-103">WPF applications that target the .NET Framework 4.7 and are running on Windows starting with Windows 10 Creators Update can enable an optional `WM_POINTER`-based WPF touch/stylus stack.</span></span>

## <a name="impact"></a><span data-ttu-id="a08b3-104">Последствия</span><span class="sxs-lookup"><span data-stu-id="a08b3-104">Impact</span></span>

<span data-ttu-id="a08b3-105">Разработчики, которые явно не включают поддержку сенсорного управления или пера на основе указателя, не должны заметить изменений в поведении сенсорного управления или пера WPF.</span><span class="sxs-lookup"><span data-stu-id="a08b3-105">Developers who do not explicitly enable pointer-based touch/stylus support should see no change in WPF touch/stylus behavior.</span></span>

<span data-ttu-id="a08b3-106">Ниже перечислены текущие известные проблемы с дополнительным стеком сенсорного управления и пера на основе `WM_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="a08b3-106">The following are current known issues with the optional `WM_POINTER`-based touch/stylus stack:</span></span>

- <span data-ttu-id="a08b3-107">Не поддерживается рукописный ввод в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="a08b3-107">No support for real-time inking.</span></span>

   <span data-ttu-id="a08b3-108">Хотя подключаемые модули рукописного ввода и пера продолжают работать, они обрабатываются в потоке пользовательского интерфейса, что может вести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="a08b3-108">While inking and stylus plugins still work, they are processed on the UI thread, which can lead to poor performance.</span></span>

- <span data-ttu-id="a08b3-109">Изменения поведения из-за изменений в переходе от событий сенсорного управления или пера к событиям мыши.</span><span class="sxs-lookup"><span data-stu-id="a08b3-109">Behavioral changes due to changes in promotion from touch/stylus events to mouse events.</span></span>

  - <span data-ttu-id="a08b3-110">Обработка может выполняться по-разному.</span><span class="sxs-lookup"><span data-stu-id="a08b3-110">Manipulation may behave differently.</span></span>

  - <span data-ttu-id="a08b3-111">При перетаскивании не будет показана соответствующая реакция на сенсорный ввод.</span><span class="sxs-lookup"><span data-stu-id="a08b3-111">Drag/Drop will not show appropriate feedback for touch input.</span></span> <span data-ttu-id="a08b3-112">(Это не влияет на ввод с помощью пера).</span><span class="sxs-lookup"><span data-stu-id="a08b3-112">(This does not affect stylus input.)</span></span>

  - <span data-ttu-id="a08b3-113">Перетаскивание больше нельзя инициировать при событиях сенсорного управления или пера.</span><span class="sxs-lookup"><span data-stu-id="a08b3-113">Drag/Drop can no longer be initiated on touch/stylus events.</span></span>

      <span data-ttu-id="a08b3-114">Это потенциально может вызвать зависание приложения до обнаружения ввода с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="a08b3-114">This can potentially cause the application to become unresponsive until mouse input is detected.</span></span> <span data-ttu-id="a08b3-115">Вместо этого разработчикам следует инициировать перетаскивание с помощью событий мыши.</span><span class="sxs-lookup"><span data-stu-id="a08b3-115">Instead, developers should initiate drag and drop from mouse events.</span></span>

## <a name="opting-in-to-wm_pointer-based-touchstylus-support"></a><span data-ttu-id="a08b3-116">Выбор поддержки сенсорного управления и пера на основе WM_POINTER</span><span class="sxs-lookup"><span data-stu-id="a08b3-116">Opting in to WM_POINTER-based touch/stylus support</span></span>

<span data-ttu-id="a08b3-117">Разработчики, желающие включить этот стек, могут добавить следующую информацию в файл *app.config* своего приложения.</span><span class="sxs-lookup"><span data-stu-id="a08b3-117">Developers who wish to enable this stack can add the following to their application's *app.config* file.</span></span>

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

<span data-ttu-id="a08b3-118">Удаление этой записи или присвоение ей значения `false` отключает данный дополнительный стек.</span><span class="sxs-lookup"><span data-stu-id="a08b3-118">Removing this entry or setting its value to `false` turns this optional stack off.</span></span>

## <a name="see-also"></a><span data-ttu-id="a08b3-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a08b3-119">See also</span></span>

- [<span data-ttu-id="a08b3-120">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="a08b3-120">Application compatibility</span></span>](application-compatibility.md)
