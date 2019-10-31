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
ms.openlocfilehash: 497a115b980bb58a3906fda68d7ff564efe78089
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127829"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="ac1ed-102">Метод ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="ac1ed-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="ac1ed-103">Проверяет переносимый исполняемый (PE) или промежуточный язык Майкрософт (MSIL) в указанном файле.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac1ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac1ed-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ac1ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac1ed-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="ac1ed-106">окне Указатель на экземпляр `IVEHandler`, который обрабатывает ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="ac1ed-107">окне Идентификатор текущего <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="ac1ed-108">окне Сочетание значений [валидаторфлагс](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) , указывающих тип проверки, которую следует выполнить.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="ac1ed-109">окне Максимальное число ошибок, которое необходимо разрешить перед выходом из проверки.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="ac1ed-110">окне Использующ.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="ac1ed-111">окне Имя проверяемого файла.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="ac1ed-112">окне Указатель на файловый буфер.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="ac1ed-113">окне Размер проверяемого файла в байтах.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac1ed-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac1ed-114">Return Value</span></span>  
  
|<span data-ttu-id="ac1ed-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac1ed-115">HRESULT</span></span>|<span data-ttu-id="ac1ed-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ac1ed-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac1ed-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac1ed-117">S_OK</span></span>|<span data-ttu-id="ac1ed-118">`Validate` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="ac1ed-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac1ed-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac1ed-120">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac1ed-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac1ed-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac1ed-122">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-122">The call timed out.</span></span>|  
|<span data-ttu-id="ac1ed-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac1ed-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac1ed-124">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac1ed-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac1ed-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac1ed-126">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac1ed-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac1ed-127">E_FAIL</span></span>|<span data-ttu-id="ac1ed-128">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac1ed-129">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac1ed-130">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac1ed-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac1ed-131">Требования</span><span class="sxs-lookup"><span data-stu-id="ac1ed-131">Requirements</span></span>  
 <span data-ttu-id="ac1ed-132">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac1ed-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac1ed-133">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="ac1ed-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="ac1ed-134">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ac1ed-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac1ed-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac1ed-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac1ed-136">См. также</span><span class="sxs-lookup"><span data-stu-id="ac1ed-136">See also</span></span>

- [<span data-ttu-id="ac1ed-137">Интерфейс ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="ac1ed-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
