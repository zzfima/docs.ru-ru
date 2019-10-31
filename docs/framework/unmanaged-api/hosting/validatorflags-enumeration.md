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
ms.openlocfilehash: 61aafb8dc99bb908fc603945ff6ea74054f812c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141421"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="d39c5-102">Перечисление ValidatorFlags</span><span class="sxs-lookup"><span data-stu-id="d39c5-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="d39c5-103">Содержит значения, указывающие тип проверки, которая должна быть выполнена при вызове метода [иклрвалидатор:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d39c5-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d39c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d39c5-104">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="d39c5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d39c5-105">Members</span></span>  
  
|<span data-ttu-id="d39c5-106">Член</span><span class="sxs-lookup"><span data-stu-id="d39c5-106">Member</span></span>|<span data-ttu-id="d39c5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d39c5-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="d39c5-108">Указывает, что следует проверять только промежуточный язык MSIL в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="d39c5-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="d39c5-109">Указывает, что должен проверяться только формат исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="d39c5-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="d39c5-110">Указывает, что следует выполнять все типы проверки и сообщать о них.</span><span class="sxs-lookup"><span data-stu-id="d39c5-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="d39c5-111">Указывает, что формат исполняемого файла не должен проверяться.</span><span class="sxs-lookup"><span data-stu-id="d39c5-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="d39c5-112">Указывает, что сообщения об ошибках проверки должны включать строки исходного кода, вызывающие ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="d39c5-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="d39c5-113">Это значение поля недопустимо в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="d39c5-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d39c5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d39c5-114">Requirements</span></span>  
 <span data-ttu-id="d39c5-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d39c5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d39c5-116">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="d39c5-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="d39c5-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d39c5-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d39c5-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d39c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39c5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d39c5-119">See also</span></span>

- [<span data-ttu-id="d39c5-120">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="d39c5-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="d39c5-121">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="d39c5-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
