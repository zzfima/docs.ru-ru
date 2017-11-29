---
title: "Перечисление ValidatorFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ValidatorFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ValidatorFlags
helpviewer_keywords: ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f283beb79ec47454185800bd772904c3c696c7c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="3c56c-102">Перечисление ValidatorFlags</span><span class="sxs-lookup"><span data-stu-id="3c56c-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="3c56c-103">Содержит значения, указывающие тип проверки, которые должны быть выполнены при обращении к [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3c56c-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c56c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c56c-104">Syntax</span></span>  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="3c56c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3c56c-105">Members</span></span>  
  
|<span data-ttu-id="3c56c-106">Член</span><span class="sxs-lookup"><span data-stu-id="3c56c-106">Member</span></span>|<span data-ttu-id="3c56c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3c56c-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="3c56c-108">Указывает, что должны быть проверены только промежуточный язык Майкрософт (MSIL) в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="3c56c-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="3c56c-109">Указывает, что должны быть проверены только формат исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="3c56c-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="3c56c-110">Указывает, следует выполнить и на всех типов проверки.</span><span class="sxs-lookup"><span data-stu-id="3c56c-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="3c56c-111">Указывает, что формат исполняемого файла не должна быть проверена.</span><span class="sxs-lookup"><span data-stu-id="3c56c-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="3c56c-112">Указывает, что сообщения об ошибках проверки должны содержать строки исходного кода, которые вызывают ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="3c56c-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="3c56c-113">Значение этого поля не поддерживается в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="3c56c-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c56c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3c56c-114">Requirements</span></span>  
 <span data-ttu-id="3c56c-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c56c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c56c-116">**Заголовок:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="3c56c-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="3c56c-117">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c56c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c56c-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c56c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c56c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3c56c-119">See Also</span></span>  
 [<span data-ttu-id="3c56c-120">Iclrerrorreportingmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3c56c-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="3c56c-121">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="3c56c-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
