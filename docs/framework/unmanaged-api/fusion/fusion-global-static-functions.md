---
title: "Глобальные статические функции Fusion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 126edd5f25b56a069a87cd1bd50cce955334a342
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="fusion-global-static-functions"></a><span data-ttu-id="cffc4-102">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="cffc4-102">Fusion Global Static Functions</span></span>
<span data-ttu-id="cffc4-103">В этом разделе описываются неуправляемые глобальные статические функции, используемые API Fusion.</span><span class="sxs-lookup"><span data-stu-id="cffc4-103">This section describes the unmanaged global static functions that the fusion API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cffc4-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="cffc4-104">In This Section</span></span>  
 [<span data-ttu-id="cffc4-105">Функция ClearDownloadCache</span><span class="sxs-lookup"><span data-stu-id="cffc4-105">ClearDownloadCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/cleardownloadcache-function.md)  
 <span data-ttu-id="cffc4-106">Очищает глобальный кэш сборок загруженных сборок.</span><span class="sxs-lookup"><span data-stu-id="cffc4-106">Clears the global assembly cache of downloaded assemblies.</span></span>  
  
 [<span data-ttu-id="cffc4-107">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="cffc4-107">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 <span data-ttu-id="cffc4-108">Сравнивает два идентификатора сборки, чтобы определить, эквивалентны ли они.</span><span class="sxs-lookup"><span data-stu-id="cffc4-108">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
 [<span data-ttu-id="cffc4-109">Функция CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="cffc4-109">CreateApplicationContext Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createapplicationcontext-function.md)  
 <span data-ttu-id="cffc4-110">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="cffc4-110">Internal only.</span></span> <span data-ttu-id="cffc4-111">(Эта функция поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода).</span><span class="sxs-lookup"><span data-stu-id="cffc4-111">(This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="cffc4-112">Функция CreateAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="cffc4-112">CreateAssemblyCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblycache-function.md)  
 <span data-ttu-id="cffc4-113">Возвращает указатель на новый [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) экземпляр, представляющий глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="cffc4-113">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
 [<span data-ttu-id="cffc4-114">Функция CreateAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="cffc4-114">CreateAssemblyEnum Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblyenum-function.md)  
 <span data-ttu-id="cffc4-115">Возвращает указатель на [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) экземпляр, который представляет список объектов, существующих в заданной сборке.</span><span class="sxs-lookup"><span data-stu-id="cffc4-115">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that represents a list of objects that exist in the specified assembly.</span></span>  
  
 [<span data-ttu-id="cffc4-116">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="cffc4-116">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 <span data-ttu-id="cffc4-117">Возвращает указатель на [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) экземпляр, представляющий уникальный идентификатор сборки с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="cffc4-117">Gets a pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
 [<span data-ttu-id="cffc4-118">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="cffc4-118">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 <span data-ttu-id="cffc4-119">Создает средство чтения журнала для указанного файла.</span><span class="sxs-lookup"><span data-stu-id="cffc4-119">Creates a history reader for the specified file.</span></span>  
  
 [<span data-ttu-id="cffc4-120">Функция CreateInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="cffc4-120">CreateInstallReferenceEnum Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createinstallreferenceenum-function.md)  
 <span data-ttu-id="cffc4-121">Возвращает указатель на [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) экземпляр, представляющий список ссылок приложения для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="cffc4-121">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
 [<span data-ttu-id="cffc4-122">Функция GetAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="cffc4-122">GetAppIdAuthority Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getappidauthority-function.md)  
 <span data-ttu-id="cffc4-123">Возвращает указатель на [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) экземпляр, который управляет ключами для идентификаторов и ссылок приложения.</span><span class="sxs-lookup"><span data-stu-id="cffc4-123">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="cffc4-124">Функция GetAssemblyIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="cffc4-124">GetAssemblyIdentityFromFile Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getassemblyidentityfromfile-function.md)  
 <span data-ttu-id="cffc4-125">Возвращает указатель на `IUnknown` объект с указанным `IID` сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="cffc4-125">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
 [<span data-ttu-id="cffc4-126">Функция GetCachePath</span><span class="sxs-lookup"><span data-stu-id="cffc4-126">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 <span data-ttu-id="cffc4-127">Возвращает путь к кэшированной сборки, используя указанные флаги.</span><span class="sxs-lookup"><span data-stu-id="cffc4-127">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
 [<span data-ttu-id="cffc4-128">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="cffc4-128">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 <span data-ttu-id="cffc4-129">Возвращает путь к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="cffc4-129">Retrieves the path of the application history directory.</span></span>  
  
 [<span data-ttu-id="cffc4-130">Функция GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="cffc4-130">GetIdentityAuthority Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getidentityauthority-function.md)  
 <span data-ttu-id="cffc4-131">Возвращает указатель на [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) экземпляр, который управляет ключи для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="cffc4-131">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
 [<span data-ttu-id="cffc4-132">Функция IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="cffc4-132">IsFrameworkAssembly Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/isframeworkassembly-function.md)  
 <span data-ttu-id="cffc4-133">Возвращает значение, указывающее, является ли указанная сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="cffc4-133">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
 [<span data-ttu-id="cffc4-134">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="cffc4-134">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 <span data-ttu-id="cffc4-135">Удаляет кэше загрузки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="cffc4-135">Deletes the common language runtime download cache.</span></span>  
  
 [<span data-ttu-id="cffc4-136">Функция PreBindAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="cffc4-136">PreBindAssemblyEx Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/prebindassemblyex-function.md)  
 <span data-ttu-id="cffc4-137">Возвращает после применения политики отображаемое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="cffc4-137">Gets the post-policy display name for an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cffc4-138">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="cffc4-138">Related Sections</span></span>  
 [<span data-ttu-id="cffc4-139">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="cffc4-139">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
  
 [<span data-ttu-id="cffc4-140">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="cffc4-140">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="cffc4-141">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="cffc4-141">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
  
 [<span data-ttu-id="cffc4-142">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="cffc4-142">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
