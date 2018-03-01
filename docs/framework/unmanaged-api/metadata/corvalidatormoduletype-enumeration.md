---
title: "Перечисление CorValidatorModuleType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3367f6928b5d7378b2686185ee3e03d0279cc11d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="ecdfc-102">Перечисление CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="ecdfc-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="ecdfc-103">Указывает тип модуля.</span><span class="sxs-lookup"><span data-stu-id="ecdfc-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdfc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecdfc-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="ecdfc-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ecdfc-105">Members</span></span>  
  
|<span data-ttu-id="ecdfc-106">Член</span><span class="sxs-lookup"><span data-stu-id="ecdfc-106">Member</span></span>|<span data-ttu-id="ecdfc-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="ecdfc-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="ecdfc-108">Модуль является недопустимым типом.</span><span class="sxs-lookup"><span data-stu-id="ecdfc-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="ecdfc-109">Минимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="ecdfc-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="ecdfc-110">Модуль является переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="ecdfc-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="ecdfc-111">Модуль является OBJ-файле.</span><span class="sxs-lookup"><span data-stu-id="ecdfc-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="ecdfc-112">Модуль является сеансом отладчика edit-and-continue.</span><span class="sxs-lookup"><span data-stu-id="ecdfc-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="ecdfc-113">Модуль является одним из пошагово строить.</span><span class="sxs-lookup"><span data-stu-id="ecdfc-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="ecdfc-114">Максимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="ecdfc-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ecdfc-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ecdfc-115">Requirements</span></span>  
 <span data-ttu-id="ecdfc-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecdfc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecdfc-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ecdfc-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ecdfc-118">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ecdfc-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ecdfc-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecdfc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecdfc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ecdfc-120">See Also</span></span>  
 [<span data-ttu-id="ecdfc-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ecdfc-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
