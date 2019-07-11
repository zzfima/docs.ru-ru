---
title: Перечисление CorDebugIlToNativeMappingTypes
ms.date: 03/30/2017
api_name:
- CorDebugIlToNativeMappingTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIlToNativeMappingTypes
helpviewer_keywords:
- CorDebugIIToNativeMappingTypes enumeration [.NET Framework debugging]
ms.assetid: c35e2919-42c3-4ba0-ae28-443c35f66f93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7d9f5373f2b4ea216ca517813b1334b9f5c38a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739966"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="3b278-102">Перечисление CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="3b278-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="3b278-103">Указывает, соответствует ли определенный диапазон машинных инструкций, представленной экземпляром структуры COR_DEBUG_IL_TO_NATIVE_MAP, области кода.</span><span class="sxs-lookup"><span data-stu-id="3b278-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b278-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b278-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="3b278-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3b278-105">Members</span></span>  
  
|<span data-ttu-id="3b278-106">Член</span><span class="sxs-lookup"><span data-stu-id="3b278-106">Member</span></span>|<span data-ttu-id="3b278-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3b278-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="3b278-108">Диапазон машинных инструкций не соответствует любой области кода.</span><span class="sxs-lookup"><span data-stu-id="3b278-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="3b278-109">Диапазон машинных инструкций соответствует пролога.</span><span class="sxs-lookup"><span data-stu-id="3b278-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="3b278-110">Диапазон машинных инструкций соответствует эпилога.</span><span class="sxs-lookup"><span data-stu-id="3b278-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b278-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3b278-111">Requirements</span></span>  
 <span data-ttu-id="3b278-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b278-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b278-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b278-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b278-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b278-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b278-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b278-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b278-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3b278-116">See also</span></span>

- [<span data-ttu-id="3b278-117">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="3b278-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="3b278-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="3b278-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
