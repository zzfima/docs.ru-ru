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
ms.openlocfilehash: 7a53b0a9cdcec33846f9d491e7d6567bcf9235b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="1ceb4-102">Функция CorLaunchApplication</span><span class="sxs-lookup"><span data-stu-id="1ceb4-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="1ceb4-103">Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.</span><span class="sxs-lookup"><span data-stu-id="1ceb4-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="1ceb4-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ceb4-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ceb4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ceb4-105">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="1ceb4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ceb4-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="1ceb4-107">[in] Значение [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) перечисление, указывающее тип узла, которое запускает приложение.</span><span class="sxs-lookup"><span data-stu-id="1ceb4-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="1ceb4-108">[in] Полное имя запускаемое приложение.</span><span class="sxs-lookup"><span data-stu-id="1ceb4-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="1ceb4-109">[in] Количество путей манифестов для приложения.</span><span class="sxs-lookup"><span data-stu-id="1ceb4-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="1ceb4-110">[in] Массив строк, каждый из которых задает путь к манифесту приложения, которое запускается.</span><span class="sxs-lookup"><span data-stu-id="1ceb4-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="1ceb4-111">[in] Число элементов данных активации для приложения, в которой запускается.</span><span class="sxs-lookup"><span data-stu-id="1ceb4-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="1ceb4-112">[in] Массив строк, каждый из которых является активации элемента данных для приложения, в которой запускается.</span><span class="sxs-lookup"><span data-stu-id="1ceb4-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="1ceb4-113">[out] Указатель на сведения о процессе, в котором был загружен приложения.</span><span class="sxs-lookup"><span data-stu-id="1ceb4-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ceb4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1ceb4-114">Requirements</span></span>  
 <span data-ttu-id="1ceb4-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ceb4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ceb4-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ceb4-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ceb4-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ceb4-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ceb4-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ceb4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ceb4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1ceb4-119">See Also</span></span>  
 [<span data-ttu-id="1ceb4-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="1ceb4-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
