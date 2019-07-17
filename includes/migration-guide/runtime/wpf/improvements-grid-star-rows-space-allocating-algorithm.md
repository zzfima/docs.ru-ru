---
ms.openlocfilehash: 770e303ab261b97efb49a3e0865a015d8de33247
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802694"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="0eb15-101">Усовершенствования алгоритма выделения пространства для строк со звездами в сетке</span><span class="sxs-lookup"><span data-stu-id="0eb15-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0eb15-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0eb15-102">Details</span></span>|<span data-ttu-id="0eb15-103">Исправлена ошибка в [алгоритме выделения размеров для ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) в <xref:System.Windows.Controls.Grid>, представленном в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="0eb15-103">Fixed a bug in the [algorithm for allocating sizes to ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="0eb15-104">В некоторых случаях, например в сетке с <code>Height=&quot;Auto&quot;</code>, которая содержит пустые строки, строки были расположены в неправильном положении, возможно, даже за пределами сетки.</span><span class="sxs-lookup"><span data-stu-id="0eb15-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="0eb15-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0eb15-105">Suggestion</span></span>|<span data-ttu-id="0eb15-106">Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.8 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="0eb15-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="0eb15-107">Область</span><span class="sxs-lookup"><span data-stu-id="0eb15-107">Scope</span></span>|<span data-ttu-id="0eb15-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="0eb15-108">Major</span></span>|
|<span data-ttu-id="0eb15-109">Версия</span><span class="sxs-lookup"><span data-stu-id="0eb15-109">Version</span></span>|<span data-ttu-id="0eb15-110">4.8</span><span class="sxs-lookup"><span data-stu-id="0eb15-110">4.8</span></span>|
|<span data-ttu-id="0eb15-111">Тип</span><span class="sxs-lookup"><span data-stu-id="0eb15-111">Type</span></span>|<span data-ttu-id="0eb15-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0eb15-112">Runtime</span></span>|

