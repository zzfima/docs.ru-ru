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
ms.openlocfilehash: 949d04fe8d9ce492fb320fb4732677ffb35302ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132828"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="7c615-102">Перечисление CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="7c615-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="7c615-103">Указывает, соответствует ли определенный диапазон машинных инструкций, представленных экземпляром структуры COR_DEBUG_IL_TO_NATIVE_MAP, специальной области кода.</span><span class="sxs-lookup"><span data-stu-id="7c615-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c615-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c615-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="7c615-105">Члены</span><span class="sxs-lookup"><span data-stu-id="7c615-105">Members</span></span>  
  
|<span data-ttu-id="7c615-106">Член</span><span class="sxs-lookup"><span data-stu-id="7c615-106">Member</span></span>|<span data-ttu-id="7c615-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7c615-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="7c615-108">Диапазон машинных инструкций не соответствует ни одной специальной области кода.</span><span class="sxs-lookup"><span data-stu-id="7c615-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="7c615-109">Диапазон машинных инструкций соответствует прологу.</span><span class="sxs-lookup"><span data-stu-id="7c615-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="7c615-110">Диапазон машинных инструкций соответствует заключительному фрагменту.</span><span class="sxs-lookup"><span data-stu-id="7c615-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c615-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7c615-111">Requirements</span></span>  
 <span data-ttu-id="7c615-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c615-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c615-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c615-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c615-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c615-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c615-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c615-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c615-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7c615-116">See also</span></span>

- [<span data-ttu-id="7c615-117">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="7c615-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="7c615-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="7c615-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
