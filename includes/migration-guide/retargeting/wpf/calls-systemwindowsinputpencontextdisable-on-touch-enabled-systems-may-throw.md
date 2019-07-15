---
ms.openlocfilehash: 0778285ef1b5702bd79743038a1bd21ba04612d6
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804328"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="5cad4-101">Вызовы System.Windows.Input.PenContext.Disable в системах с поддержкой сенсорного ввода могут вызвать исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="5cad4-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5cad4-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="5cad4-102">Details</span></span>|<span data-ttu-id="5cad4-103">В некоторых случаях вызовы внутреннего метода <strong>System.Windows.Intput.PenContext.Disable</strong> в системах с поддержкой сенсорного ввода могут вызывать необработанное исключение <code>T:System.ArgumentException</code> из-за повторного входа.</span><span class="sxs-lookup"><span data-stu-id="5cad4-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="5cad4-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="5cad4-104">Suggestion</span></span>|<span data-ttu-id="5cad4-105">Эта проблема была устранена в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="5cad4-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="5cad4-106">Чтобы это исключение не возникало, выполните обновление до версии платформы .NET Framework 4.7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="5cad4-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="5cad4-107">Область</span><span class="sxs-lookup"><span data-stu-id="5cad4-107">Scope</span></span>|<span data-ttu-id="5cad4-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="5cad4-108">Edge</span></span>|
|<span data-ttu-id="5cad4-109">Версия</span><span class="sxs-lookup"><span data-stu-id="5cad4-109">Version</span></span>|<span data-ttu-id="5cad4-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="5cad4-110">4.6.1</span></span>|
|<span data-ttu-id="5cad4-111">Тип</span><span class="sxs-lookup"><span data-stu-id="5cad4-111">Type</span></span>|<span data-ttu-id="5cad4-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="5cad4-112">Retargeting</span></span>|

