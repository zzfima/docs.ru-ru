---
ms.openlocfilehash: ee5070a1a4c58d6c1282ba47c921436ca22722ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858493"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="93d9c-101">.NET Framework 4.6 не использует версию 4.5.x.x для собственной регистрации в реестре</span><span class="sxs-lookup"><span data-stu-id="93d9c-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="93d9c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="93d9c-102">Details</span></span>|<span data-ttu-id="93d9c-103">Ключ версии, установленный в реестре (<code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) для платформы .NET Framework 4.6, ожидаемо начинается с "4.6", а не с "4.5".</span><span class="sxs-lookup"><span data-stu-id="93d9c-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="93d9c-104">Приложения, которые используют эти разделы реестра для определения установленных на компьютере версий .NET Framework, следует обновить таким образом, чтобы понимать, что 4.6 — это новая возможная версия, совместимая с предыдущими выпусками 4.5.x.</span><span class="sxs-lookup"><span data-stu-id="93d9c-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="93d9c-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="93d9c-105">Suggestion</span></span>|<span data-ttu-id="93d9c-106">Обновите приложения, проверяющие установку версию .NET Framework 4.5 в соответствующих разделах реестра, так, чтобы они принимали версию 4.6.</span><span class="sxs-lookup"><span data-stu-id="93d9c-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="93d9c-107">Область</span><span class="sxs-lookup"><span data-stu-id="93d9c-107">Scope</span></span>|<span data-ttu-id="93d9c-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="93d9c-108">Edge</span></span>|
|<span data-ttu-id="93d9c-109">Version</span><span class="sxs-lookup"><span data-stu-id="93d9c-109">Version</span></span>|<span data-ttu-id="93d9c-110">4.6</span><span class="sxs-lookup"><span data-stu-id="93d9c-110">4.6</span></span>|
|<span data-ttu-id="93d9c-111">Type</span><span class="sxs-lookup"><span data-stu-id="93d9c-111">Type</span></span>|<span data-ttu-id="93d9c-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="93d9c-112">Runtime</span></span>|
