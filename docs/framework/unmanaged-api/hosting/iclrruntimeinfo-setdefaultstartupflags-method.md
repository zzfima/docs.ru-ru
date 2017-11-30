---
title: "Метод ICLRRuntimeInfo::SetDefaultStartupFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.SetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1732073b9799453bd32447e7a688b0280e66f1ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="3e249-102">Метод ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="3e249-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="3e249-103">Задает флаги загрузки и файл конфигурации узла, который будет использоваться для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3e249-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="3e249-104">Этот метод заменяет использование `startupFlags` параметр в [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="3e249-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e249-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e249-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e249-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e249-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="3e249-107">[in] Флаги запуска узла, который следует установить.</span><span class="sxs-lookup"><span data-stu-id="3e249-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="3e249-108">Используйте те же флаги, как и с [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="3e249-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="3e249-109">[in] Файл конфигурации главного узла, чтобы задать путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="3e249-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e249-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e249-110">Return Value</span></span>  
 <span data-ttu-id="3e249-111">Этот метод возвращает следующий заданный HRESULT а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="3e249-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3e249-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e249-112">HRESULT</span></span>|<span data-ttu-id="3e249-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3e249-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e249-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e249-114">S_OK</span></span>|<span data-ttu-id="3e249-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="3e249-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e249-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e249-116">Remarks</span></span>  
 <span data-ttu-id="3e249-117">Многопоточные узел должен синхронизировать вызовы этого метода.</span><span class="sxs-lookup"><span data-stu-id="3e249-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="3e249-118">В противном случае поток A может вызвать `SetStartupFlags` метод после завершения вызова потока B `SetStartupFlags` и перед поток B запускает среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="3e249-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e249-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3e249-119">Requirements</span></span>  
 <span data-ttu-id="3e249-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e249-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e249-121">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3e249-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3e249-122">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e249-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e249-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e249-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e249-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3e249-124">See Also</span></span>  
 [<span data-ttu-id="3e249-125">ICLRRuntimeInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3e249-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="3e249-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3e249-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="3e249-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="3e249-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
