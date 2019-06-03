---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379580"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="4208c-101">Не следует использовать iPad в файле пользовательских возможностей, так как теперь это функция браузера</span><span class="sxs-lookup"><span data-stu-id="4208c-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4208c-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4208c-102">Details</span></span>|<span data-ttu-id="4208c-103">Начиная с версии .NET Framework 4.5 iPad является идентификатором в файле возможностей браузера ASP.NET по умолчанию, поэтому его не следует использовать в файле пользовательских возможностей</span><span class="sxs-lookup"><span data-stu-id="4208c-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>|
|<span data-ttu-id="4208c-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="4208c-104">Suggestion</span></span>|<span data-ttu-id="4208c-105">Если требуются определенные возможности iPad, необходимо изменить поведение iPad, настроив возможности на предварительно определенном шлюзе refID &quot;IPad&quot; или создав новый идентификатор &quot;IPad&quot; путем сопоставления агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="4208c-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>|
|<span data-ttu-id="4208c-106">Область</span><span class="sxs-lookup"><span data-stu-id="4208c-106">Scope</span></span>|<span data-ttu-id="4208c-107">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="4208c-107">Edge</span></span>|
|<span data-ttu-id="4208c-108">Версия</span><span class="sxs-lookup"><span data-stu-id="4208c-108">Version</span></span>|<span data-ttu-id="4208c-109">4.5</span><span class="sxs-lookup"><span data-stu-id="4208c-109">4.5</span></span>|
|<span data-ttu-id="4208c-110">Тип</span><span class="sxs-lookup"><span data-stu-id="4208c-110">Type</span></span>|<span data-ttu-id="4208c-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4208c-111">Runtime</span></span>|
