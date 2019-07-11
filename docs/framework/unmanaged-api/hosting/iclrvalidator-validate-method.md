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
ms.openlocfilehash: d5fbf83690f616556774e8f279e1077fccdb8baf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779914"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="bc3ad-102">Метод ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="bc3ad-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="bc3ad-103">Проверяет переносимого исполняемого (PE) или промежуточного языка Майкрософт (MSIL) в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc3ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc3ad-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="bc3ad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc3ad-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="bc3ad-106">[in] Указатель на `IVEHandler` экземпляр, который обрабатывает ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="bc3ad-107">[in] Идентификатор для текущего <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="bc3ad-108">[in] Сочетание [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) значений, указывающих на вид проверки, которые должны быть выполнены.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="bc3ad-109">[in] Максимальное количество ошибок, чтобы разрешить перед выходом из проверки.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="bc3ad-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="bc3ad-111">[in] Имя проверяемого файла.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="bc3ad-112">[in] Указатель буфера файла.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="bc3ad-113">[in] Размер в байтах файла для проверки.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc3ad-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bc3ad-114">Return Value</span></span>  
  
|<span data-ttu-id="bc3ad-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc3ad-115">HRESULT</span></span>|<span data-ttu-id="bc3ad-116">Описание</span><span class="sxs-lookup"><span data-stu-id="bc3ad-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc3ad-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc3ad-117">S_OK</span></span>|<span data-ttu-id="bc3ad-118">`Validate` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="bc3ad-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bc3ad-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bc3ad-120">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bc3ad-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bc3ad-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bc3ad-122">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-122">The call timed out.</span></span>|  
|<span data-ttu-id="bc3ad-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bc3ad-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bc3ad-124">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bc3ad-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bc3ad-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bc3ad-126">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bc3ad-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bc3ad-127">E_FAIL</span></span>|<span data-ttu-id="bc3ad-128">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bc3ad-129">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bc3ad-130">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bc3ad-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc3ad-131">Требования</span><span class="sxs-lookup"><span data-stu-id="bc3ad-131">Requirements</span></span>  
 <span data-ttu-id="bc3ad-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc3ad-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc3ad-133">**Заголовок.** IValidator.idl в файле IValidator.h</span><span class="sxs-lookup"><span data-stu-id="bc3ad-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="bc3ad-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc3ad-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc3ad-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc3ad-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3ad-136">См. также</span><span class="sxs-lookup"><span data-stu-id="bc3ad-136">See also</span></span>

- [<span data-ttu-id="bc3ad-137">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="bc3ad-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
