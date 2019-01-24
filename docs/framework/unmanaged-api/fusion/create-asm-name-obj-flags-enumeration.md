---
title: Перечисление CREATE_ASM_NAME_OBJ_FLAGS
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4da0e064f507e2330aac27fc5c8bcd56b9d3c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716236"
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="1a8a7-102">Перечисление CREATE_ASM_NAME_OBJ_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1a8a7-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="1a8a7-103">Указывает атрибуты [IAssemblyName-интерфейс](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта при построении с [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="1a8a7-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a8a7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a8a7-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1a8a7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="1a8a7-105">Members</span></span>  
  
|<span data-ttu-id="1a8a7-106">Член</span><span class="sxs-lookup"><span data-stu-id="1a8a7-106">Member</span></span>|<span data-ttu-id="1a8a7-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="1a8a7-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="1a8a7-108">Указывает, что переданный параметр является текстовым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="1a8a7-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="1a8a7-109">Задает несколько значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a8a7-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="1a8a7-110">Проверяет правило дружественной сборки (только имя и открытый ключ).</span><span class="sxs-lookup"><span data-stu-id="1a8a7-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="1a8a7-111">Этот член является только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="1a8a7-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="1a8a7-112">Сочетание `CANOF_PARSE_DISPLAY_NAME` и `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` флаги.</span><span class="sxs-lookup"><span data-stu-id="1a8a7-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="1a8a7-113">Этот член является только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="1a8a7-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a8a7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1a8a7-114">Requirements</span></span>  
 <span data-ttu-id="1a8a7-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a8a7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a8a7-116">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="1a8a7-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1a8a7-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a8a7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8a7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1a8a7-118">See also</span></span>
- [<span data-ttu-id="1a8a7-119">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="1a8a7-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="1a8a7-120">Функция CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="1a8a7-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [<span data-ttu-id="1a8a7-121">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="1a8a7-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
