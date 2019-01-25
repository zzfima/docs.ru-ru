---
title: Перечисление ValidatorFlags
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e982fa7f6354f341ff4718440f345e282a1d20d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492226"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="3932b-102">Перечисление ValidatorFlags</span><span class="sxs-lookup"><span data-stu-id="3932b-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="3932b-103">Содержит значения, указывающие тип проверки, которое должно выполняться при вызове [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3932b-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3932b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3932b-104">Syntax</span></span>  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="3932b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3932b-105">Members</span></span>  
  
|<span data-ttu-id="3932b-106">Член</span><span class="sxs-lookup"><span data-stu-id="3932b-106">Member</span></span>|<span data-ttu-id="3932b-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="3932b-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="3932b-108">Указывает, что должна быть проверена только промежуточный язык Майкрософт (MSIL) в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="3932b-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="3932b-109">Указывает, что должна быть проверена только формат исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="3932b-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="3932b-110">Указывает, что выполнены все типы проверки и они будут составляться.</span><span class="sxs-lookup"><span data-stu-id="3932b-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="3932b-111">Указывает, что формат исполняемого файла не должна быть проверена.</span><span class="sxs-lookup"><span data-stu-id="3932b-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="3932b-112">Указывает, что сообщения об ошибках проверки должны содержать строки исходного кода, которые вызывают ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="3932b-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="3932b-113">Значение этого поля не допускается в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="3932b-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3932b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3932b-114">Requirements</span></span>  
 <span data-ttu-id="3932b-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3932b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3932b-116">**Заголовок.** IValidator.idl в файле IValidator.h</span><span class="sxs-lookup"><span data-stu-id="3932b-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="3932b-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3932b-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3932b-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3932b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3932b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3932b-119">See also</span></span>
- [<span data-ttu-id="3932b-120">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="3932b-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="3932b-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="3932b-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
