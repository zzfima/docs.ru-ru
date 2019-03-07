---
title: Метод ICLRRuntimeInfo::SetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 440f2f7c542c697b3d817c988211303c60073979
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492365"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="3e694-102">Метод ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="3e694-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="3e694-103">Задает флаги запуска и файле конфигурации главного узла, который будет использоваться для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3e694-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="3e694-104">Этот метод заменяет `startupFlags` параметр в [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="3e694-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e694-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e694-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e694-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e694-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="3e694-107">[in] Флаги запуска узла, для установки.</span><span class="sxs-lookup"><span data-stu-id="3e694-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="3e694-108">Используйте те же флаги, как и с [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="3e694-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="3e694-109">[in] Файл конфигурации узла, чтобы задать путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="3e694-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e694-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e694-110">Return Value</span></span>  
 <span data-ttu-id="3e694-111">Этот метод возвращает следующие конкретных ошибках HRESULT а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="3e694-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3e694-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e694-112">HRESULT</span></span>|<span data-ttu-id="3e694-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3e694-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e694-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e694-114">S_OK</span></span>|<span data-ttu-id="3e694-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="3e694-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e694-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e694-116">Remarks</span></span>  
 <span data-ttu-id="3e694-117">Многопоточные узла необходимо синхронизировать вызовы этого метода.</span><span class="sxs-lookup"><span data-stu-id="3e694-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="3e694-118">В противном случае может вызывать потока A `SetStartupFlags` метод после завершения вызова потока B `SetStartupFlags` и прежде, чем поток B запускает среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="3e694-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e694-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3e694-119">Requirements</span></span>  
 <span data-ttu-id="3e694-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e694-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e694-121">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3e694-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3e694-122">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e694-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e694-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e694-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e694-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3e694-124">See also</span></span>
- [<span data-ttu-id="3e694-125">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="3e694-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="3e694-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3e694-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="3e694-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="3e694-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
