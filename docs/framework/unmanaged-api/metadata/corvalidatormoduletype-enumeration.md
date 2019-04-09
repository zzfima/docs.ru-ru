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
ms.openlocfilehash: 14eee096c25967d321e4693b260501827d944a80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154184"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="f29a4-102">Перечисление CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="f29a4-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="f29a4-103">Указывает тип модуля.</span><span class="sxs-lookup"><span data-stu-id="f29a4-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f29a4-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f29a4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f29a4-105">Members</span></span>  
  
|<span data-ttu-id="f29a4-106">Член</span><span class="sxs-lookup"><span data-stu-id="f29a4-106">Member</span></span>|<span data-ttu-id="f29a4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f29a4-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="f29a4-108">Модуль является недопустимым типом.</span><span class="sxs-lookup"><span data-stu-id="f29a4-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="f29a4-109">Минимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="f29a4-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="f29a4-110">Модуль — это файл переносимого исполняемого (PE).</span><span class="sxs-lookup"><span data-stu-id="f29a4-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="f29a4-111">Модуль является OBJ-файле.</span><span class="sxs-lookup"><span data-stu-id="f29a4-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="f29a4-112">Модуль является сеанс отладчика, изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="f29a4-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="f29a4-113">Модуль — это приложения, пошаговое построение.</span><span class="sxs-lookup"><span data-stu-id="f29a4-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="f29a4-114">Максимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="f29a4-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f29a4-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f29a4-115">Requirements</span></span>  
 <span data-ttu-id="f29a4-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f29a4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f29a4-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f29a4-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f29a4-118">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f29a4-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f29a4-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f29a4-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f29a4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f29a4-120">See also</span></span>

- [<span data-ttu-id="f29a4-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="f29a4-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
