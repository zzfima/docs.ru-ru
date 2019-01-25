---
title: Метод ICLRRuntimeInfo::GetProcAddress
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f956ed33e0a168dca0c0e5de92d38ba32db3fb05
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703462"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="7e9e2-102">Метод ICLRRuntimeInfo::GetProcAddress</span><span class="sxs-lookup"><span data-stu-id="7e9e2-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="7e9e2-103">Получает адрес заданной функции, которая была экспортирована из общеязыковой среды выполнения (CLR), связанных с этим интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="7e9e2-104">Этот метод заменяет [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e9e2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e9e2-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e9e2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e9e2-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="7e9e2-107">[in] Имя экспортируемой функции.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="7e9e2-108">[out] Адрес экспортированной функции.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e9e2-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7e9e2-109">Return Value</span></span>  
 <span data-ttu-id="7e9e2-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7e9e2-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e9e2-111">HRESULT</span></span>|<span data-ttu-id="7e9e2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7e9e2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e9e2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e9e2-113">S_OK</span></span>|<span data-ttu-id="7e9e2-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="7e9e2-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7e9e2-115">E_POINTER</span></span>|<span data-ttu-id="7e9e2-116">`pszProcName` или `ppProc` равно null.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="7e9e2-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="7e9e2-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="7e9e2-118">Указанная функция не экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e9e2-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e9e2-119">Remarks</span></span>  
 <span data-ttu-id="7e9e2-120">Этот метод вызывает среды CLR загружено, но не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="7e9e2-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e9e2-121">Требования</span><span class="sxs-lookup"><span data-stu-id="7e9e2-121">Requirements</span></span>  
 <span data-ttu-id="7e9e2-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e9e2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e9e2-123">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7e9e2-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7e9e2-124">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e9e2-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e9e2-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e9e2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9e2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7e9e2-126">See also</span></span>
- [<span data-ttu-id="7e9e2-127">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="7e9e2-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7e9e2-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="7e9e2-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7e9e2-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="7e9e2-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
