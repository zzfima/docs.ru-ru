---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237614"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="ff28c-101">Усовершенствования алгоритма выделения пространства для строк со звездами в сетке</span><span class="sxs-lookup"><span data-stu-id="ff28c-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ff28c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ff28c-102">Details</span></span>|<span data-ttu-id="ff28c-103">Исправлена ошибка в [алгоритме выделения размеров для ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) в <xref:System.Windows.Controls.Grid>, представленном в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="ff28c-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="ff28c-104">В некоторых случаях, например в сетке с <code>Height=&quot;Auto&quot;</code>, которая содержит пустые строки, строки были расположены в неправильном положении, возможно, даже за пределами сетки.</span><span class="sxs-lookup"><span data-stu-id="ff28c-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="ff28c-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="ff28c-105">Suggestion</span></span>|<span data-ttu-id="ff28c-106">Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.8 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="ff28c-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="ff28c-107">Область</span><span class="sxs-lookup"><span data-stu-id="ff28c-107">Scope</span></span>|<span data-ttu-id="ff28c-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="ff28c-108">Major</span></span>|
|<span data-ttu-id="ff28c-109">Version</span><span class="sxs-lookup"><span data-stu-id="ff28c-109">Version</span></span>|<span data-ttu-id="ff28c-110">4.8</span><span class="sxs-lookup"><span data-stu-id="ff28c-110">4.8</span></span>|
|<span data-ttu-id="ff28c-111">Type</span><span class="sxs-lookup"><span data-stu-id="ff28c-111">Type</span></span>|<span data-ttu-id="ff28c-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="ff28c-112">Runtime</span></span>|
