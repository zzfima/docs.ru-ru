---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804960"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="8b954-101">Адаптеры потока WinRT больше не вызывают FlushAsync автоматически при закрытии</span><span class="sxs-lookup"><span data-stu-id="8b954-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8b954-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8b954-102">Details</span></span>|<span data-ttu-id="8b954-103">В приложениях для магазина Windows адаптеры потока среды выполнения Windows больше не вызывают метод FlushAsync из метода Dispose.</span><span class="sxs-lookup"><span data-stu-id="8b954-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>|
|<span data-ttu-id="8b954-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="8b954-104">Suggestion</span></span>|<span data-ttu-id="8b954-105">Это изменение должно быть прозрачным.</span><span class="sxs-lookup"><span data-stu-id="8b954-105">This change should be transparent.</span></span> <span data-ttu-id="8b954-106">Разработчики могут восстановить прежнее поведение, написав следующий код.</span><span class="sxs-lookup"><span data-stu-id="8b954-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="8b954-107">Область</span><span class="sxs-lookup"><span data-stu-id="8b954-107">Scope</span></span>|<span data-ttu-id="8b954-108">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="8b954-108">Transparent</span></span>|
|<span data-ttu-id="8b954-109">Версия</span><span class="sxs-lookup"><span data-stu-id="8b954-109">Version</span></span>|<span data-ttu-id="8b954-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="8b954-110">4.5.1</span></span>|
|<span data-ttu-id="8b954-111">Тип</span><span class="sxs-lookup"><span data-stu-id="8b954-111">Type</span></span>|<span data-ttu-id="8b954-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="8b954-112">Runtime</span></span>|
