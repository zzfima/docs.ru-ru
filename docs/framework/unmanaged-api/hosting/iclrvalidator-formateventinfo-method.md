---
title: Метод ICLRValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
ms.openlocfilehash: 935d8e9fa3ed15be03c6cd05b1bc3c4919d0cc2b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127859"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="1d78b-102">Метод ICLRValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="1d78b-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="1d78b-103">Возвращает подробное сообщение об указанной ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="1d78b-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d78b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d78b-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d78b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d78b-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="1d78b-106">окне Значение HRESULT, которое было передано обработчику ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="1d78b-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="1d78b-107">окне Экземпляр `VEContext`, содержащий контекстные сведения об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="1d78b-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="1d78b-108">[вход, выход] Понятное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1d78b-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="1d78b-109">окне Максимальная длина сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="1d78b-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="1d78b-110">окне Защищенный массив дополнительных параметров, которые будут использоваться в сообщении.</span><span class="sxs-lookup"><span data-stu-id="1d78b-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d78b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1d78b-111">Return Value</span></span>  
  
|<span data-ttu-id="1d78b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d78b-112">HRESULT</span></span>|<span data-ttu-id="1d78b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1d78b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d78b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d78b-114">S_OK</span></span>|<span data-ttu-id="1d78b-115">`FormatEventInfo` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="1d78b-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="1d78b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d78b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d78b-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1d78b-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d78b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d78b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d78b-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="1d78b-119">The call timed out.</span></span>|  
|<span data-ttu-id="1d78b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d78b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d78b-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="1d78b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d78b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d78b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d78b-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="1d78b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d78b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d78b-124">E_FAIL</span></span>|<span data-ttu-id="1d78b-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="1d78b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d78b-126">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1d78b-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d78b-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d78b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d78b-128">Требования</span><span class="sxs-lookup"><span data-stu-id="1d78b-128">Requirements</span></span>  
 <span data-ttu-id="1d78b-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d78b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d78b-130">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="1d78b-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="1d78b-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1d78b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d78b-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d78b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d78b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="1d78b-133">See also</span></span>

- [<span data-ttu-id="1d78b-134">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="1d78b-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="1d78b-135">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="1d78b-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
