---
title: Метод ICLRValidator::Validate
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2ad9ef473a498804e5b3ac0469b5b68697c49f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="5a566-102">Метод ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="5a566-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="5a566-103">Проверяет переносимого исполняемого (PE) или промежуточного языка Майкрософт (MSIL) в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="5a566-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a566-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a566-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);      
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a566-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a566-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="5a566-106">[in] Указатель на `IVEHandler` экземпляр, который обрабатывает ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="5a566-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="5a566-107">[in] Идентификатор для текущего <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="5a566-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="5a566-108">[in] Сочетание [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) значения, указывающие тип проверки, которую необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="5a566-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="5a566-109">[in] Максимальное число ошибок, чтобы перед выходом из проверки.</span><span class="sxs-lookup"><span data-stu-id="5a566-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="5a566-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="5a566-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="5a566-111">[in] Имя файла, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="5a566-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="5a566-112">[in] Указатель буфера файла.</span><span class="sxs-lookup"><span data-stu-id="5a566-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="5a566-113">[in] Размер в байтах файла, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="5a566-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a566-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5a566-114">Return Value</span></span>  
  
|<span data-ttu-id="5a566-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a566-115">HRESULT</span></span>|<span data-ttu-id="5a566-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5a566-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a566-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a566-117">S_OK</span></span>|<span data-ttu-id="5a566-118">`Validate` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5a566-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="5a566-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a566-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a566-120">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5a566-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a566-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a566-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a566-122">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="5a566-122">The call timed out.</span></span>|  
|<span data-ttu-id="5a566-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a566-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a566-124">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="5a566-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a566-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a566-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a566-126">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="5a566-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a566-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a566-127">E_FAIL</span></span>|<span data-ttu-id="5a566-128">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="5a566-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a566-129">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5a566-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a566-130">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5a566-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a566-131">Требования</span><span class="sxs-lookup"><span data-stu-id="5a566-131">Requirements</span></span>  
 <span data-ttu-id="5a566-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a566-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a566-133">**Заголовок:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="5a566-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="5a566-134">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a566-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a566-135">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a566-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a566-136">См. также</span><span class="sxs-lookup"><span data-stu-id="5a566-136">See Also</span></span>  
 [<span data-ttu-id="5a566-137">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="5a566-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
