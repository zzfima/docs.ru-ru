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
ms.openlocfilehash: ee1cfe52caa9d727a132d7adc23b03575293db65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716782"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="ac4da-102">Перечисление CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="ac4da-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="ac4da-103">Указывает тип модуля.</span><span class="sxs-lookup"><span data-stu-id="ac4da-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac4da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac4da-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ac4da-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ac4da-105">Members</span></span>  
  
|<span data-ttu-id="ac4da-106">Член</span><span class="sxs-lookup"><span data-stu-id="ac4da-106">Member</span></span>|<span data-ttu-id="ac4da-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ac4da-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="ac4da-108">Модуль является недопустимым типом.</span><span class="sxs-lookup"><span data-stu-id="ac4da-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="ac4da-109">Минимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="ac4da-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="ac4da-110">Модуль — это файл переносимого исполняемого (PE).</span><span class="sxs-lookup"><span data-stu-id="ac4da-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="ac4da-111">Модуль является OBJ-файле.</span><span class="sxs-lookup"><span data-stu-id="ac4da-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="ac4da-112">Модуль является сеанс отладчика, изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="ac4da-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="ac4da-113">Модуль — это приложения, пошаговое построение.</span><span class="sxs-lookup"><span data-stu-id="ac4da-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="ac4da-114">Максимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="ac4da-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac4da-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ac4da-115">Requirements</span></span>  
 <span data-ttu-id="ac4da-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac4da-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac4da-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ac4da-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac4da-118">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac4da-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac4da-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac4da-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac4da-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ac4da-120">See also</span></span>
- [<span data-ttu-id="ac4da-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ac4da-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
