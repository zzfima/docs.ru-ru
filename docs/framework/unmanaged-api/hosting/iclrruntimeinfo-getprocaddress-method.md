---
title: "Метод ICLRRuntimeInfo::GetProcAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2878b23a2f848657e1d26b3bfb8395f8897c0632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="e7765-102">Метод ICLRRuntimeInfo::GetProcAddress</span><span class="sxs-lookup"><span data-stu-id="e7765-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="e7765-103">Получает адрес указанной функции, которая была экспортирована из общеязыковой среды выполнения (CLR), связанных с этим интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="e7765-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="e7765-104">Этот метод заменяет [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="e7765-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7765-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7765-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7765-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7765-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="e7765-107">[in] Имя экспортируемой функции.</span><span class="sxs-lookup"><span data-stu-id="e7765-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="e7765-108">[out] Адрес экспортированной функции.</span><span class="sxs-lookup"><span data-stu-id="e7765-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7765-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7765-109">Return Value</span></span>  
 <span data-ttu-id="e7765-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="e7765-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e7765-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7765-111">HRESULT</span></span>|<span data-ttu-id="e7765-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e7765-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7765-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7765-113">S_OK</span></span>|<span data-ttu-id="e7765-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e7765-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="e7765-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e7765-115">E_POINTER</span></span>|<span data-ttu-id="e7765-116">`pszProcName` или `ppProc` равно null.</span><span class="sxs-lookup"><span data-stu-id="e7765-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="e7765-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="e7765-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="e7765-118">Указанная функция не экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="e7765-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7765-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7765-119">Remarks</span></span>  
 <span data-ttu-id="e7765-120">Этот метод вызывает средой CLR с целью загружено, но не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="e7765-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7765-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e7765-121">Requirements</span></span>  
 <span data-ttu-id="e7765-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7765-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7765-123">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e7765-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e7765-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7765-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7765-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7765-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7765-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e7765-126">See Also</span></span>  
 [<span data-ttu-id="e7765-127">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="e7765-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="e7765-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e7765-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e7765-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="e7765-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
