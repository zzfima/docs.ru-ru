---
title: Функция CorLaunchApplication
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9861de733a9acb43c7e2a4b4941f9945fc5f0ba7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758375"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="9531f-102">Функция CorLaunchApplication</span><span class="sxs-lookup"><span data-stu-id="9531f-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="9531f-103">Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.</span><span class="sxs-lookup"><span data-stu-id="9531f-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="9531f-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9531f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9531f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9531f-105">Syntax</span></span>  
  
```cpp  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9531f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9531f-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="9531f-107">[in] Значение [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) перечисление, указывающее тип узла, которое запускает приложение.</span><span class="sxs-lookup"><span data-stu-id="9531f-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="9531f-108">[in] Полное имя приложения, запускаемый.</span><span class="sxs-lookup"><span data-stu-id="9531f-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="9531f-109">[in] Количество путей манифестов для приложения.</span><span class="sxs-lookup"><span data-stu-id="9531f-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="9531f-110">[in] Массив строк, каждый из которых указывает путь к манифесту приложения, запускаемый.</span><span class="sxs-lookup"><span data-stu-id="9531f-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="9531f-111">[in] Число элементов данных активации для приложения, запускаемый.</span><span class="sxs-lookup"><span data-stu-id="9531f-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="9531f-112">[in] Массив строк, каждый из которых представляет элемент данных активации для приложения, запускаемый.</span><span class="sxs-lookup"><span data-stu-id="9531f-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="9531f-113">[out] Указатель на сведения о процессе, в котором было загружено приложение.</span><span class="sxs-lookup"><span data-stu-id="9531f-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9531f-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9531f-114">Requirements</span></span>  
 <span data-ttu-id="9531f-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9531f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9531f-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9531f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9531f-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9531f-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9531f-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9531f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9531f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9531f-119">See also</span></span>

- [<span data-ttu-id="9531f-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="9531f-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
