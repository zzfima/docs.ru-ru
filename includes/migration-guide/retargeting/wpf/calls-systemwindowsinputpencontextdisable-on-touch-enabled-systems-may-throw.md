---
ms.openlocfilehash: 3cd5052dffcb059c240a310e0b89384f28409264
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234546"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="97ba5-101">Вызовы System.Windows.Input.PenContext.Disable в системах с поддержкой сенсорного ввода могут вызвать исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="97ba5-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="97ba5-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="97ba5-102">Details</span></span>|<span data-ttu-id="97ba5-103">В некоторых случаях вызовы внутреннего метода <strong>System.Windows.Intput.PenContext.Disable</strong> в системах с поддержкой сенсорного ввода могут вызывать необработанное исключение <code>T:System.ArgumentException</code> из-за повторного входа.</span><span class="sxs-lookup"><span data-stu-id="97ba5-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="97ba5-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="97ba5-104">Suggestion</span></span>|<span data-ttu-id="97ba5-105">Эта проблема была устранена в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="97ba5-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="97ba5-106">Чтобы это исключение не возникало, выполните обновление до версии платформы .NET Framework 4.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="97ba5-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="97ba5-107">Область</span><span class="sxs-lookup"><span data-stu-id="97ba5-107">Scope</span></span>|<span data-ttu-id="97ba5-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="97ba5-108">Edge</span></span>|
|<span data-ttu-id="97ba5-109">Версия</span><span class="sxs-lookup"><span data-stu-id="97ba5-109">Version</span></span>|<span data-ttu-id="97ba5-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="97ba5-110">4.6.1</span></span>|
|<span data-ttu-id="97ba5-111">Тип</span><span class="sxs-lookup"><span data-stu-id="97ba5-111">Type</span></span>|<span data-ttu-id="97ba5-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="97ba5-112">Retargeting</span></span>|
