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
ms.openlocfilehash: 04bed418d96658e29328cf2ce6bba445639b437f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750755"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="34a03-102">Перечисление CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="34a03-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="34a03-103">Указывает тип модуля.</span><span class="sxs-lookup"><span data-stu-id="34a03-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34a03-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="34a03-105">Участники</span><span class="sxs-lookup"><span data-stu-id="34a03-105">Members</span></span>  
  
|<span data-ttu-id="34a03-106">Член</span><span class="sxs-lookup"><span data-stu-id="34a03-106">Member</span></span>|<span data-ttu-id="34a03-107">Описание</span><span class="sxs-lookup"><span data-stu-id="34a03-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="34a03-108">Модуль является недопустимым типом.</span><span class="sxs-lookup"><span data-stu-id="34a03-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="34a03-109">Минимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="34a03-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="34a03-110">Модуль — это файл переносимого исполняемого (PE).</span><span class="sxs-lookup"><span data-stu-id="34a03-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="34a03-111">Модуль является OBJ-файле.</span><span class="sxs-lookup"><span data-stu-id="34a03-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="34a03-112">Модуль является сеанс отладчика, изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="34a03-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="34a03-113">Модуль — это приложения, пошаговое построение.</span><span class="sxs-lookup"><span data-stu-id="34a03-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="34a03-114">Максимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="34a03-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="34a03-115">Требования</span><span class="sxs-lookup"><span data-stu-id="34a03-115">Requirements</span></span>  
 <span data-ttu-id="34a03-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34a03-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34a03-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34a03-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34a03-118">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34a03-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34a03-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34a03-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a03-120">См. также</span><span class="sxs-lookup"><span data-stu-id="34a03-120">See also</span></span>

- [<span data-ttu-id="34a03-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="34a03-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
