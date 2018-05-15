---
title: Метод IValidator::Validate
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf2c343db459879ca95372e104aee68b22dee6b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="72e46-102">Метод IValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="72e46-102">IValidator::Validate Method</span></span>
<span data-ttu-id="72e46-103">Проверяет заданный переносимый исполняемый (PE) или файл Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="72e46-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72e46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72e46-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72e46-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72e46-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="72e46-106">[in] Указатель на `IVEHandler` экземпляр, который обрабатывает ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="72e46-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="72e46-107">[in] Указатель на домен приложения, в которой загружается указанный файл.</span><span class="sxs-lookup"><span data-stu-id="72e46-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="72e46-108">[in] Побитовое сочетание [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) значений, указывающее, проверки, которые необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="72e46-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="72e46-109">[in] Максимальное число ошибок, чтобы перед выходом из проверки.</span><span class="sxs-lookup"><span data-stu-id="72e46-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="72e46-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="72e46-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="72e46-111">[in] Строка, указывающая имя файла, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="72e46-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="72e46-112">[in] Указатель на буфер памяти, в которой хранится файл.</span><span class="sxs-lookup"><span data-stu-id="72e46-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="72e46-113">[in] Размер в байтах файла, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="72e46-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72e46-114">Требования</span><span class="sxs-lookup"><span data-stu-id="72e46-114">Requirements</span></span>  
 <span data-ttu-id="72e46-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72e46-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72e46-116">**Заголовок:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="72e46-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="72e46-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72e46-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72e46-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72e46-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e46-119">См. также</span><span class="sxs-lookup"><span data-stu-id="72e46-119">See Also</span></span>  
 
