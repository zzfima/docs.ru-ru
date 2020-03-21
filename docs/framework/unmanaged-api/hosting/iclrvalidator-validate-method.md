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
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178064"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="dd512-102">Метод ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="dd512-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="dd512-103">Проверяет портативный исполняемый (PE) или промежуточный язык Microsoft (MSIL) в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="dd512-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd512-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd512-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="dd512-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd512-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="dd512-106">(в) Указатель на `IVEHandler` экземпляр, обрабатывая ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="dd512-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="dd512-107">(в) Идентификатор <xref:System.AppDomain>для текущего .</span><span class="sxs-lookup"><span data-stu-id="dd512-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="dd512-108">(в) Комбинация значений [ValidatorFlags,](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) указывающая на вид проверки, которая должна быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="dd512-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="dd512-109">(в) Максимальное количество ошибок, которые можно разрешить перед выходом из проверки.</span><span class="sxs-lookup"><span data-stu-id="dd512-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="dd512-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="dd512-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="dd512-111">(в) Имя файла, которое должно быть проверено.</span><span class="sxs-lookup"><span data-stu-id="dd512-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="dd512-112">(в) Указатель на буфер файла.</span><span class="sxs-lookup"><span data-stu-id="dd512-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="dd512-113">(в) Размер файла, в байтах, должен быть проверен.</span><span class="sxs-lookup"><span data-stu-id="dd512-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd512-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dd512-114">Return Value</span></span>  
  
|<span data-ttu-id="dd512-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd512-115">HRESULT</span></span>|<span data-ttu-id="dd512-116">Описание</span><span class="sxs-lookup"><span data-stu-id="dd512-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd512-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd512-117">S_OK</span></span>|<span data-ttu-id="dd512-118">`Validate`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="dd512-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="dd512-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd512-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd512-120">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dd512-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd512-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd512-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd512-122">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="dd512-122">The call timed out.</span></span>|  
|<span data-ttu-id="dd512-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd512-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd512-124">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="dd512-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd512-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd512-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd512-126">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="dd512-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd512-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd512-127">E_FAIL</span></span>|<span data-ttu-id="dd512-128">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="dd512-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd512-129">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="dd512-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd512-130">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd512-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd512-131">Требования</span><span class="sxs-lookup"><span data-stu-id="dd512-131">Requirements</span></span>  
 <span data-ttu-id="dd512-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd512-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd512-133">**Заголовок:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="dd512-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="dd512-134">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd512-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd512-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd512-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd512-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dd512-136">See also</span></span>

- [<span data-ttu-id="dd512-137">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="dd512-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
