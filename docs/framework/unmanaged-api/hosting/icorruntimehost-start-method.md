---
title: Метод ICorRuntimeHost::Start
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96e8d80e2dff88aa5a589f864278b4a4e9cc76ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="6a756-102">Метод ICorRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="6a756-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="6a756-103">Запускает общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="6a756-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a756-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a756-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6a756-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6a756-105">Return Value</span></span>  
  
|<span data-ttu-id="6a756-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a756-106">HRESULT</span></span>|<span data-ttu-id="6a756-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6a756-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a756-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a756-108">S_OK</span></span>|<span data-ttu-id="6a756-109">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="6a756-109">The operation was successful.</span></span>|  
|<span data-ttu-id="6a756-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6a756-110">S_FALSE</span></span>|<span data-ttu-id="6a756-111">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="6a756-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6a756-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6a756-112">E_FAIL</span></span>|<span data-ttu-id="6a756-113">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="6a756-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6a756-114">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6a756-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="6a756-115">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6a756-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6a756-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6a756-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6a756-117">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6a756-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a756-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a756-118">Remarks</span></span>  
 <span data-ttu-id="6a756-119">Это обычно не нужно вызывать `Start` метода, так как среда CLR автоматически запускается при первом запросе для запуска управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="6a756-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a756-120">Требования</span><span class="sxs-lookup"><span data-stu-id="6a756-120">Requirements</span></span>  
 <span data-ttu-id="6a756-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a756-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a756-122">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a756-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a756-123">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a756-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a756-124">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6a756-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a756-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6a756-125">See Also</span></span>  
 [<span data-ttu-id="6a756-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6a756-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
