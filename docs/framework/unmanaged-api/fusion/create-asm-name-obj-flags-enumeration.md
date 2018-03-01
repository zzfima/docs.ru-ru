---
title: "Перечисление CREATE_ASM_NAME_OBJ_FLAGS"
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
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 61e9bea623e38b1416721773d8739bc6e6748909
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="f8138-102">Перечисление CREATE_ASM_NAME_OBJ_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f8138-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="f8138-103">Задает атрибуты [IAssemblyName-интерфейс](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта при построении с [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="f8138-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8138-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8138-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="f8138-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f8138-105">Members</span></span>  
  
|<span data-ttu-id="f8138-106">Член</span><span class="sxs-lookup"><span data-stu-id="f8138-106">Member</span></span>|<span data-ttu-id="f8138-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="f8138-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="f8138-108">Указывает, что переданный параметр является текстовым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="f8138-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="f8138-109">Задает несколько значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f8138-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="f8138-110">Проверяет правило дружественной сборки (только имя и открытый ключ).</span><span class="sxs-lookup"><span data-stu-id="f8138-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="f8138-111">Этот член представляет только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="f8138-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="f8138-112">Сочетание `CANOF_PARSE_DISPLAY_NAME` и `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` флаги.</span><span class="sxs-lookup"><span data-stu-id="f8138-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="f8138-113">Этот член представляет только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="f8138-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8138-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f8138-114">Requirements</span></span>  
 <span data-ttu-id="f8138-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8138-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8138-116">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f8138-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f8138-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8138-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8138-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f8138-118">See Also</span></span>  
 [<span data-ttu-id="f8138-119">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="f8138-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="f8138-120">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="f8138-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 [<span data-ttu-id="f8138-121">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="f8138-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
