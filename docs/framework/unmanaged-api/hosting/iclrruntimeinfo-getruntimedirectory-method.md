---
title: Метод ICLRRuntimeInfo::GetRuntimeDirectory
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2455c896ebdc12f2bb92a30d55745f7bd5bc308a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765520"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="95bb2-102">Метод ICLRRuntimeInfo::GetRuntimeDirectory</span><span class="sxs-lookup"><span data-stu-id="95bb2-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="95bb2-103">Получает каталог установки общеязыковой среды выполнения (CLR), связанных с этим интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="95bb2-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="95bb2-104">Этот метод заменяет [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) функция, предоставленная в .NET Framework версий 2.0, 3.0 и 3.5.</span><span class="sxs-lookup"><span data-stu-id="95bb2-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95bb2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95bb2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95bb2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="95bb2-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="95bb2-107">[out] Возвращает каталог установки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="95bb2-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="95bb2-108">Путь установки будет полностью; например «c:\windows\microsoft.net\framework\v1.0.3705\\«.</span><span class="sxs-lookup"><span data-stu-id="95bb2-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="95bb2-109">[in, out] Указывает размер `pwzBuffer` для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="95bb2-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="95bb2-110">Если `pwzBuffer` имеет значение null, `pchBuffer` возвращает требуемый размер `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="95bb2-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95bb2-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="95bb2-111">Return Value</span></span>  
 <span data-ttu-id="95bb2-112">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="95bb2-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="95bb2-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95bb2-113">HRESULT</span></span>|<span data-ttu-id="95bb2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="95bb2-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95bb2-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="95bb2-115">S_OK</span></span>|<span data-ttu-id="95bb2-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="95bb2-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="95bb2-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="95bb2-117">E_POINTER</span></span>|<span data-ttu-id="95bb2-118">`pwzBuffer` или `pchBuffer` равно null.</span><span class="sxs-lookup"><span data-stu-id="95bb2-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95bb2-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="95bb2-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95bb2-120">Требования</span><span class="sxs-lookup"><span data-stu-id="95bb2-120">Requirements</span></span>  
 <span data-ttu-id="95bb2-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95bb2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95bb2-122">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="95bb2-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="95bb2-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95bb2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95bb2-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95bb2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bb2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="95bb2-125">See also</span></span>

- [<span data-ttu-id="95bb2-126">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="95bb2-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="95bb2-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="95bb2-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
