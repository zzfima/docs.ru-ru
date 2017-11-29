---
title: "Метод ICLRRuntimeInfo::GetProcAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetProcAddress
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b8af06a52a3961bb3e551375350dee849343b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="c67cc-102">Метод ICLRRuntimeInfo::GetProcAddress</span><span class="sxs-lookup"><span data-stu-id="c67cc-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="c67cc-103">Получает адрес указанной функции, которая была экспортирована из общеязыковой среды выполнения (CLR), связанных с этим интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="c67cc-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="c67cc-104">Этот метод заменяет [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="c67cc-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c67cc-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c67cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c67cc-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="c67cc-107">[in] Имя экспортируемой функции.</span><span class="sxs-lookup"><span data-stu-id="c67cc-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="c67cc-108">[out] Адрес экспортированной функции.</span><span class="sxs-lookup"><span data-stu-id="c67cc-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c67cc-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c67cc-109">Return Value</span></span>  
 <span data-ttu-id="c67cc-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="c67cc-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c67cc-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c67cc-111">HRESULT</span></span>|<span data-ttu-id="c67cc-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c67cc-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c67cc-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c67cc-113">S_OK</span></span>|<span data-ttu-id="c67cc-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="c67cc-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c67cc-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c67cc-115">E_POINTER</span></span>|<span data-ttu-id="c67cc-116">`pszProcName` или `ppProc` равно null.</span><span class="sxs-lookup"><span data-stu-id="c67cc-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="c67cc-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="c67cc-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="c67cc-118">Указанная функция не экспортированную функцию.</span><span class="sxs-lookup"><span data-stu-id="c67cc-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c67cc-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="c67cc-119">Remarks</span></span>  
 <span data-ttu-id="c67cc-120">Этот метод вызывает средой CLR с целью загружено, но не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="c67cc-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c67cc-121">Требования</span><span class="sxs-lookup"><span data-stu-id="c67cc-121">Requirements</span></span>  
 <span data-ttu-id="c67cc-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c67cc-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c67cc-123">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c67cc-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c67cc-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c67cc-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c67cc-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c67cc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c67cc-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c67cc-126">See Also</span></span>  
 [<span data-ttu-id="c67cc-127">ICLRRuntimeInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c67cc-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="c67cc-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c67cc-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="c67cc-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="c67cc-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
