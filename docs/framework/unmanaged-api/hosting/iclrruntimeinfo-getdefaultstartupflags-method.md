---
title: Метод ICLRRuntimeInfo::GetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c39ad4638c7db45c481bd3dfccb0a82759397aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072588"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="856ce-102">Метод ICLRRuntimeInfo::GetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="856ce-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="856ce-103">Получает флаги загрузки и файл конфигурации узла, который будет использоваться для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="856ce-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="856ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="856ce-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="856ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="856ce-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="856ce-106">[out] Указатель на флаги запуска узла, которые в настоящее время заданы.</span><span class="sxs-lookup"><span data-stu-id="856ce-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="856ce-107">[out] Указатель на путь к каталогу текущего файла конфигурации узла.</span><span class="sxs-lookup"><span data-stu-id="856ce-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="856ce-108">[in, out] На входе размер `pwzHostConfigFile`, чтобы избежать переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="856ce-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="856ce-109">Если `pwzHostConfigFile` имеет значение null, метод возвращает требуемый размер `pwzHostConfigFile` для предварительного выделения.</span><span class="sxs-lookup"><span data-stu-id="856ce-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="856ce-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="856ce-110">Return Value</span></span>  
 <span data-ttu-id="856ce-111">Этот метод возвращает следующие конкретных ошибках HRESULT а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="856ce-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="856ce-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="856ce-112">HRESULT</span></span>|<span data-ttu-id="856ce-113">Описание</span><span class="sxs-lookup"><span data-stu-id="856ce-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="856ce-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="856ce-114">S_OK</span></span>|<span data-ttu-id="856ce-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="856ce-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="856ce-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="856ce-116">Remarks</span></span>  
 <span data-ttu-id="856ce-117">Этот метод возвращает значения по умолчанию флаг (`STARTUP_CONCURRENT_GC` и `NULL`), или значения, предоставленные предыдущего вызова [метод ICLRRuntimeInfo::SetDefaultStartupFlags](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), или значения, заданные по любому `CorBind*` методы, если они привязаны к этой среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="856ce-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="856ce-118">Требования</span><span class="sxs-lookup"><span data-stu-id="856ce-118">Requirements</span></span>  
 <span data-ttu-id="856ce-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="856ce-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="856ce-120">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="856ce-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="856ce-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="856ce-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="856ce-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="856ce-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856ce-123">См. также</span><span class="sxs-lookup"><span data-stu-id="856ce-123">See also</span></span>

- [<span data-ttu-id="856ce-124">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="856ce-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="856ce-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="856ce-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="856ce-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="856ce-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
