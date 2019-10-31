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
ms.openlocfilehash: 8ae47eac713fbee30ea543538957b12460b8e1fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123274"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="cc351-102">Метод IValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="cc351-102">IValidator::Validate Method</span></span>
<span data-ttu-id="cc351-103">Проверяет указанный переносимый исполняемый (PE) или промежуточный язык MSIL-файл.</span><span class="sxs-lookup"><span data-stu-id="cc351-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc351-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc351-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="cc351-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc351-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="cc351-106">окне Указатель на экземпляр `IVEHandler`, который обрабатывает ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="cc351-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="cc351-107">окне Указатель на домен приложения, в который загружается файл.</span><span class="sxs-lookup"><span data-stu-id="cc351-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="cc351-108">окне Побитовое сочетание значений [валидаторфлагс](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) , указывающее, какие проверки должны быть выполнены.</span><span class="sxs-lookup"><span data-stu-id="cc351-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="cc351-109">окне Максимальное число ошибок, которое необходимо разрешить перед выходом из проверки.</span><span class="sxs-lookup"><span data-stu-id="cc351-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="cc351-110">окне Не используется.</span><span class="sxs-lookup"><span data-stu-id="cc351-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="cc351-111">окне Строка, указывающая имя проверяемого файла.</span><span class="sxs-lookup"><span data-stu-id="cc351-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="cc351-112">окне Указатель на буфер памяти, в котором хранится файл.</span><span class="sxs-lookup"><span data-stu-id="cc351-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="cc351-113">окне Размер проверяемого файла в байтах.</span><span class="sxs-lookup"><span data-stu-id="cc351-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc351-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cc351-114">Requirements</span></span>  
 <span data-ttu-id="cc351-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc351-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc351-116">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="cc351-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="cc351-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc351-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc351-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc351-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
