---
title: Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dcddb5766894a30f1ccb2552a09abe7153c6eea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434956"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="ebb9d-102">Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="ebb9d-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="ebb9d-103">Вызывает указанный метод заданного типа в заданной управляемой сборке.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebb9d-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ebb9d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebb9d-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="ebb9d-106">[in] Путь к <xref:System.Reflection.Assembly> , определяющий <xref:System.Type> — метод которого должен быть вызван.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="ebb9d-107">[in] Имя <xref:System.Type> , определяющий вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="ebb9d-108">[in] Имя вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="ebb9d-109">[in] Параметр строки для передачи в метод.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="ebb9d-110">[out] Целочисленное значение, возвращаемое вызываемым методом.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebb9d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ebb9d-111">Return Value</span></span>  
  
|<span data-ttu-id="ebb9d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ebb9d-112">HRESULT</span></span>|<span data-ttu-id="ebb9d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ebb9d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebb9d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebb9d-114">S_OK</span></span>|<span data-ttu-id="ebb9d-115">`ExecuteInDefaultAppDomain` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="ebb9d-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ebb9d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ebb9d-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ebb9d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ebb9d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ebb9d-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-119">The call timed out.</span></span>|  
|<span data-ttu-id="ebb9d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ebb9d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ebb9d-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ebb9d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ebb9d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ebb9d-123">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ebb9d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ebb9d-124">E_FAIL</span></span>|<span data-ttu-id="ebb9d-125">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ebb9d-126">Если метод вернет значение E_FAIL, список отзыва Сертификатов больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="ebb9d-127">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebb9d-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="ebb9d-128">Remarks</span></span>  
 <span data-ttu-id="ebb9d-129">Вызываемый метод должен иметь следующую сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="ebb9d-129">The invoked method must have the following signature:</span></span>  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="ebb9d-130">где `pwzMethodName` представляет имя вызываемого метода и `pwzArgument` представляет строковое значение, передаваемый как параметр этого метода.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="ebb9d-131">Если значение HRESULT равно S_OK, `pReturnValue` присвоено целочисленное значение, возвращаемое вызываемым методом.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="ebb9d-132">В противном случае `pReturnValue` не задано.</span><span class="sxs-lookup"><span data-stu-id="ebb9d-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebb9d-133">Требования</span><span class="sxs-lookup"><span data-stu-id="ebb9d-133">Requirements</span></span>  
 <span data-ttu-id="ebb9d-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebb9d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebb9d-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ebb9d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebb9d-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebb9d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebb9d-137">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebb9d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb9d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="ebb9d-138">See Also</span></span>  
 [<span data-ttu-id="ebb9d-139">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ebb9d-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
