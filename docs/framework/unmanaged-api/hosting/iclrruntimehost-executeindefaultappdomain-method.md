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
ms.openlocfilehash: 1a1bc7609042422de876fe167a9e61655aaf62b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176413"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="5edd0-102">Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="5edd0-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="5edd0-103">Вызывает указанный метод указанного типа в указанной управляемой сборке.</span><span class="sxs-lookup"><span data-stu-id="5edd0-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5edd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5edd0-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5edd0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5edd0-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="5edd0-106">(в) Путь к <xref:System.Reflection.Assembly> тому, <xref:System.Type> который определяет метод, который должен вызываться.</span><span class="sxs-lookup"><span data-stu-id="5edd0-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="5edd0-107">(в) <xref:System.Type> Название, определяющее метод для ввода.</span><span class="sxs-lookup"><span data-stu-id="5edd0-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="5edd0-108">(в) Название метода для ввода.</span><span class="sxs-lookup"><span data-stu-id="5edd0-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="5edd0-109">(в) Параметр строки для передачи методу.</span><span class="sxs-lookup"><span data-stu-id="5edd0-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="5edd0-110">(ваут) Значение цельное возвращается усылаемым методом.</span><span class="sxs-lookup"><span data-stu-id="5edd0-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5edd0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5edd0-111">Return Value</span></span>  
  
|<span data-ttu-id="5edd0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5edd0-112">HRESULT</span></span>|<span data-ttu-id="5edd0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5edd0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5edd0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5edd0-114">S_OK</span></span>|<span data-ttu-id="5edd0-115">`ExecuteInDefaultAppDomain`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="5edd0-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="5edd0-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5edd0-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5edd0-117">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5edd0-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5edd0-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5edd0-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5edd0-119">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="5edd0-119">The call timed out.</span></span>|  
|<span data-ttu-id="5edd0-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5edd0-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5edd0-121">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="5edd0-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5edd0-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5edd0-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5edd0-123">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="5edd0-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5edd0-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5edd0-124">E_FAIL</span></span>|<span data-ttu-id="5edd0-125">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="5edd0-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5edd0-126">Если метод возвращается E_FAIL, CRL больше не может быть пригоден к удочку в процессе.</span><span class="sxs-lookup"><span data-stu-id="5edd0-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="5edd0-127">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5edd0-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5edd0-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="5edd0-128">Remarks</span></span>  
 <span data-ttu-id="5edd0-129">Усылаемый метод должен иметь следующую подпись:</span><span class="sxs-lookup"><span data-stu-id="5edd0-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="5edd0-130">где `pwzMethodName` представлено имя вызываемого `pwzArgument` метода и представлено значение строки, передаваемое в качестве параметра этому методу.</span><span class="sxs-lookup"><span data-stu-id="5edd0-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="5edd0-131">Если значение HRESULT настроено `pReturnValue` на S_OK, устанавливается к значению integer, возвращаемому вызовуемым методом.</span><span class="sxs-lookup"><span data-stu-id="5edd0-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="5edd0-132">В `pReturnValue` противном случае, не устанавливается.</span><span class="sxs-lookup"><span data-stu-id="5edd0-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5edd0-133">Требования</span><span class="sxs-lookup"><span data-stu-id="5edd0-133">Requirements</span></span>  
 <span data-ttu-id="5edd0-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5edd0-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5edd0-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5edd0-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5edd0-136">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5edd0-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5edd0-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5edd0-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5edd0-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5edd0-138">See also</span></span>

- [<span data-ttu-id="5edd0-139">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5edd0-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
