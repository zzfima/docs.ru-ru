---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887830"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="3b3bb-101">Вызовы System.Windows.Input.PenContext.Disable в системах с поддержкой сенсорного ввода могут вызвать исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="3b3bb-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3b3bb-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3b3bb-102">Details</span></span>|<span data-ttu-id="3b3bb-103">В некоторых случаях вызовы внутреннего метода **System.Windows.Intput.PenContext.Disable** в системах с поддержкой сенсорного ввода могут вызывать необработанное исключение <code>T:System.ArgumentException</code> из-за повторного входа.</span><span class="sxs-lookup"><span data-stu-id="3b3bb-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="3b3bb-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="3b3bb-104">Suggestion</span></span>|<span data-ttu-id="3b3bb-105">Эта проблема была устранена в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="3b3bb-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="3b3bb-106">Чтобы это исключение не возникало, выполните обновление до версии платформы .NET Framework 4.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="3b3bb-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="3b3bb-107">Область</span><span class="sxs-lookup"><span data-stu-id="3b3bb-107">Scope</span></span>|<span data-ttu-id="3b3bb-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="3b3bb-108">Edge</span></span>|
|<span data-ttu-id="3b3bb-109">Version</span><span class="sxs-lookup"><span data-stu-id="3b3bb-109">Version</span></span>|<span data-ttu-id="3b3bb-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="3b3bb-110">4.6.1</span></span>|
|<span data-ttu-id="3b3bb-111">Type</span><span class="sxs-lookup"><span data-stu-id="3b3bb-111">Type</span></span>|<span data-ttu-id="3b3bb-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="3b3bb-112">Retargeting</span></span>|
