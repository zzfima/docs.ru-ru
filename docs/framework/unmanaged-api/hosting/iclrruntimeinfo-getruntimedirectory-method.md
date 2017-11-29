---
title: "Метод ICLRRuntimeInfo::GetRuntimeDirectory"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetRuntimeDirectory
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddaca8232f0b262377c7915852da89cecec09993
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="fbc02-102">Метод ICLRRuntimeInfo::GetRuntimeDirectory</span><span class="sxs-lookup"><span data-stu-id="fbc02-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="fbc02-103">Получает каталог установки общеязыковой среды выполнения (CLR), связанных с этим интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="fbc02-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="fbc02-104">Этот метод заменяет [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) функции, предоставляемые в .NET Framework версии 2.0, 3.0 и 3.5.</span><span class="sxs-lookup"><span data-stu-id="fbc02-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbc02-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbc02-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fbc02-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbc02-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="fbc02-107">[out] Возвращает каталог установки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="fbc02-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="fbc02-108">Путь установки — полностью; например «c:\windows\microsoft.net\framework\v1.0.3705\\».</span><span class="sxs-lookup"><span data-stu-id="fbc02-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="fbc02-109">[in, out] Указывает размер `pwzBuffer` для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="fbc02-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="fbc02-110">Если `pwzBuffer` имеет значение null, `pchBuffer` возвращает требуемый размер `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="fbc02-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbc02-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fbc02-111">Return Value</span></span>  
 <span data-ttu-id="fbc02-112">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="fbc02-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fbc02-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbc02-113">HRESULT</span></span>|<span data-ttu-id="fbc02-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fbc02-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbc02-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbc02-115">S_OK</span></span>|<span data-ttu-id="fbc02-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="fbc02-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="fbc02-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fbc02-117">E_POINTER</span></span>|<span data-ttu-id="fbc02-118">`pwzBuffer` или `pchBuffer` равно null.</span><span class="sxs-lookup"><span data-stu-id="fbc02-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbc02-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="fbc02-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbc02-120">Требования</span><span class="sxs-lookup"><span data-stu-id="fbc02-120">Requirements</span></span>  
 <span data-ttu-id="fbc02-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbc02-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbc02-122">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fbc02-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fbc02-123">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fbc02-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbc02-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbc02-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc02-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fbc02-125">See Also</span></span>  
 [<span data-ttu-id="fbc02-126">ICLRRuntimeInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fbc02-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="fbc02-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="fbc02-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
