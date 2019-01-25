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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31b99ce4435c1282380291e3c3c15723381e8ab4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741851"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="efb8a-102">Метод ICLRValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="efb8a-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="efb8a-103">Возвращает подробное сообщение об ошибке проверки указанной.</span><span class="sxs-lookup"><span data-stu-id="efb8a-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efb8a-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efb8a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efb8a-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="efb8a-106">[in] Значение HRESULT, который был передан в обработчик ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="efb8a-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="efb8a-107">[in] Объект `VEContext` экземпляр, содержащий контекстные сведения об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="efb8a-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="efb8a-108">[in, out] Понятное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="efb8a-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="efb8a-109">[in] Максимальная длина сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="efb8a-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="efb8a-110">[in] Безопасный массив дополнительных параметров для использования в сообщении.</span><span class="sxs-lookup"><span data-stu-id="efb8a-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efb8a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="efb8a-111">Return Value</span></span>  
  
|<span data-ttu-id="efb8a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efb8a-112">HRESULT</span></span>|<span data-ttu-id="efb8a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="efb8a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="efb8a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="efb8a-114">S_OK</span></span>|<span data-ttu-id="efb8a-115">`FormatEventInfo` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="efb8a-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="efb8a-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="efb8a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="efb8a-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="efb8a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="efb8a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="efb8a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="efb8a-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="efb8a-119">The call timed out.</span></span>|  
|<span data-ttu-id="efb8a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="efb8a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="efb8a-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="efb8a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="efb8a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="efb8a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="efb8a-123">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="efb8a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="efb8a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="efb8a-124">E_FAIL</span></span>|<span data-ttu-id="efb8a-125">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="efb8a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="efb8a-126">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="efb8a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="efb8a-127">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="efb8a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efb8a-128">Требования</span><span class="sxs-lookup"><span data-stu-id="efb8a-128">Requirements</span></span>  
 <span data-ttu-id="efb8a-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efb8a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb8a-130">**Заголовок.** IValidator.idl в файле IValidator.h</span><span class="sxs-lookup"><span data-stu-id="efb8a-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="efb8a-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="efb8a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efb8a-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb8a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb8a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="efb8a-133">See also</span></span>
- [<span data-ttu-id="efb8a-134">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="efb8a-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="efb8a-135">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="efb8a-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
