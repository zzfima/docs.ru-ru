---
title: Глобальные статические функции Fusion
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a8f15bc862c0486311960f7567c49424859846e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795318"
---
# <a name="fusion-global-static-functions"></a><span data-ttu-id="3658d-102">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="3658d-102">Fusion Global Static Functions</span></span>
<span data-ttu-id="3658d-103">В этом разделе описаны неуправляемые глобальные статические функции, используемые API Fusion.</span><span class="sxs-lookup"><span data-stu-id="3658d-103">This section describes the unmanaged global static functions that the fusion API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3658d-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3658d-104">In This Section</span></span>  
 [<span data-ttu-id="3658d-105">Функция ClearDownloadCache</span><span class="sxs-lookup"><span data-stu-id="3658d-105">ClearDownloadCache Function</span></span>](cleardownloadcache-function.md)  
 <span data-ttu-id="3658d-106">Очищает глобальный кэш сборок скачанных сборок.</span><span class="sxs-lookup"><span data-stu-id="3658d-106">Clears the global assembly cache of downloaded assemblies.</span></span>  
  
 [<span data-ttu-id="3658d-107">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="3658d-107">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)  
 <span data-ttu-id="3658d-108">Сравнивает два идентификатора сборки, чтобы определить, являются ли они эквивалентными.</span><span class="sxs-lookup"><span data-stu-id="3658d-108">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
 [<span data-ttu-id="3658d-109">Функция CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="3658d-109">CreateApplicationContext Function</span></span>](createapplicationcontext-function.md)  
 <span data-ttu-id="3658d-110">Только внутренние.</span><span class="sxs-lookup"><span data-stu-id="3658d-110">Internal only.</span></span> <span data-ttu-id="3658d-111">(Эта функция поддерживает инфраструктуру .NET Framework и не предназначена для непосредственного использования в коде.)</span><span class="sxs-lookup"><span data-stu-id="3658d-111">(This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="3658d-112">Функция CreateAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="3658d-112">CreateAssemblyCache Function</span></span>](createassemblycache-function.md)  
 <span data-ttu-id="3658d-113">Возвращает указатель на новый экземпляр [IAssemblyCache](iassemblycache-interface.md) , представляющий глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="3658d-113">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
 [<span data-ttu-id="3658d-114">Функция CreateAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="3658d-114">CreateAssemblyEnum Function</span></span>](createassemblyenum-function.md)  
 <span data-ttu-id="3658d-115">Возвращает указатель на экземпляр [IAssemblyEnum](iassemblyenum-interface.md) , представляющий список объектов, существующих в указанной сборке.</span><span class="sxs-lookup"><span data-stu-id="3658d-115">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that represents a list of objects that exist in the specified assembly.</span></span>  
  
 [<span data-ttu-id="3658d-116">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="3658d-116">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)  
 <span data-ttu-id="3658d-117">Возвращает указатель на экземпляр [IAssemblyName](iassemblyname-interface.md) , представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="3658d-117">Gets a pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
 [<span data-ttu-id="3658d-118">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="3658d-118">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)  
 <span data-ttu-id="3658d-119">Создает средство чтения журнала для указанного файла.</span><span class="sxs-lookup"><span data-stu-id="3658d-119">Creates a history reader for the specified file.</span></span>  
  
 [<span data-ttu-id="3658d-120">Функция CreateInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="3658d-120">CreateInstallReferenceEnum Function</span></span>](createinstallreferenceenum-function.md)  
 <span data-ttu-id="3658d-121">Возвращает указатель на экземпляр [IInstallReferenceEnum](iinstallreferenceenum-interface.md) , представляющий список ссылок приложения на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="3658d-121">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
 [<span data-ttu-id="3658d-122">Функция GetAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="3658d-122">GetAppIdAuthority Function</span></span>](getappidauthority-function.md)  
 <span data-ttu-id="3658d-123">Возвращает указатель на экземпляр [иаппидаусорити](iappidauthority-interface.md) , который управляет ключами для удостоверений приложений и ссылок.</span><span class="sxs-lookup"><span data-stu-id="3658d-123">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="3658d-124">Функция GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="3658d-124">GetAssemblyIdentityFromFile Function</span></span>](getassemblyidentityfromfile-function.md)  
 <span data-ttu-id="3658d-125">Возвращает указатель на `IUnknown` объект с указанным `IID` в сборке по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="3658d-125">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
 [<span data-ttu-id="3658d-126">Функция GetCachePath</span><span class="sxs-lookup"><span data-stu-id="3658d-126">GetCachePath Function</span></span>](getcachepath-function.md)  
 <span data-ttu-id="3658d-127">Возвращает путь к кэшированной сборке с использованием указанных флагов.</span><span class="sxs-lookup"><span data-stu-id="3658d-127">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
 [<span data-ttu-id="3658d-128">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="3658d-128">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)  
 <span data-ttu-id="3658d-129">Возвращает путь к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="3658d-129">Retrieves the path of the application history directory.</span></span>  
  
 [<span data-ttu-id="3658d-130">Функция GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="3658d-130">GetIdentityAuthority Function</span></span>](getidentityauthority-function.md)  
 <span data-ttu-id="3658d-131">Возвращает указатель на экземпляр [IIdentityAuthority](iidentityauthority-interface.md) , который управляет ключами для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="3658d-131">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
 [<span data-ttu-id="3658d-132">Функция IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="3658d-132">IsFrameworkAssembly Function</span></span>](isframeworkassembly-function.md)  
 <span data-ttu-id="3658d-133">Возвращает значение, указывающее, является ли указанная сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="3658d-133">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
 [<span data-ttu-id="3658d-134">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="3658d-134">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)  
 <span data-ttu-id="3658d-135">Удаляет кэш загрузки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3658d-135">Deletes the common language runtime download cache.</span></span>  
  
 [<span data-ttu-id="3658d-136">Функция PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="3658d-136">PreBindAssemblyEx Function</span></span>](prebindassemblyex-function.md)  
 <span data-ttu-id="3658d-137">Возвращает отображаемое имя после применения политики для сборки.</span><span class="sxs-lookup"><span data-stu-id="3658d-137">Gets the post-policy display name for an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3658d-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3658d-138">Related Sections</span></span>  
 [<span data-ttu-id="3658d-139">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="3658d-139">Fusion Interfaces</span></span>](fusion-interfaces.md)  
  
 [<span data-ttu-id="3658d-140">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="3658d-140">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="3658d-141">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="3658d-141">Fusion Structures</span></span>](fusion-structures.md)  
  
 [<span data-ttu-id="3658d-142">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="3658d-142">Global Assembly Cache</span></span>](../../app-domains/gac.md)
