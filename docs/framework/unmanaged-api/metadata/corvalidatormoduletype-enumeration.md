---
title: Перечисление CorValidatorModuleType
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97e9ae5a7c35b4f9b6e2b4ca7e754b5b7480dfa6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444143"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="7c0c9-102">Перечисление CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="7c0c9-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="7c0c9-103">Указывает тип модуля.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c0c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c0c9-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="7c0c9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7c0c9-105">Members</span></span>  
  
|<span data-ttu-id="7c0c9-106">Член</span><span class="sxs-lookup"><span data-stu-id="7c0c9-106">Member</span></span>|<span data-ttu-id="7c0c9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7c0c9-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="7c0c9-108">Модуль является недопустимым типом.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="7c0c9-109">Минимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="7c0c9-110">Модуль является переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="7c0c9-111">Модуль является OBJ-файле.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="7c0c9-112">Модуль является сеансом отладчика edit-and-continue.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="7c0c9-113">Модуль является одним из пошагово строить.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="7c0c9-114">Максимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="7c0c9-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c0c9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="7c0c9-115">Requirements</span></span>  
 <span data-ttu-id="7c0c9-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c0c9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0c9-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c0c9-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c0c9-118">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c0c9-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c0c9-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0c9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0c9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7c0c9-120">See Also</span></span>  
 [<span data-ttu-id="7c0c9-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7c0c9-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
