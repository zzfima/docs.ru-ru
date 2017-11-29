---
title: "Метод ICLRRuntimeInfo::GetDefaultStartupFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73ad12e99a1ba98f6ea61775155cf1389118f754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="8ceff-102">Метод ICLRRuntimeInfo::GetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="8ceff-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="8ceff-103">Получает флаги загрузки и файл конфигурации главного узла, который будет использоваться для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8ceff-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ceff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ceff-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ceff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ceff-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="8ceff-106">[out] Указатель флаги запуска узлов, заданных в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="8ceff-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="8ceff-107">[out] Указатель на путь к каталогу файла конфигурации текущего узла.</span><span class="sxs-lookup"><span data-stu-id="8ceff-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="8ceff-108">[in, out] На входе, размер `pwzHostConfigFile`, чтобы избежать переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="8ceff-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="8ceff-109">Если `pwzHostConfigFile` имеет значение null, метод возвращает требуемый размер `pwzHostConfigFile` для предварительного выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="8ceff-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ceff-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8ceff-110">Return Value</span></span>  
 <span data-ttu-id="8ceff-111">Этот метод возвращает следующий заданный HRESULT а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="8ceff-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8ceff-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ceff-112">HRESULT</span></span>|<span data-ttu-id="8ceff-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8ceff-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ceff-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ceff-114">S_OK</span></span>|<span data-ttu-id="8ceff-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="8ceff-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ceff-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ceff-116">Remarks</span></span>  
 <span data-ttu-id="8ceff-117">Этот метод возвращает значения по умолчанию флаг (`STARTUP_CONCURRENT_GC` и `NULL`), или значения, предоставленные предыдущего вызова [ICLRRuntimeInfo::setdefaultstartupflags-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), или значения, заданные с помощью любого из `CorBind*` методы, если они были привязаны к данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8ceff-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ceff-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8ceff-118">Requirements</span></span>  
 <span data-ttu-id="8ceff-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ceff-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ceff-120">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8ceff-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8ceff-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ceff-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ceff-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ceff-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ceff-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8ceff-123">See Also</span></span>  
 [<span data-ttu-id="8ceff-124">ICLRRuntimeInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8ceff-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="8ceff-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8ceff-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="8ceff-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="8ceff-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
