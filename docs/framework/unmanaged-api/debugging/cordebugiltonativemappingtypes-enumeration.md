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
ms.openlocfilehash: 2f62707fb1e52a96cf3f131e9c11fee82ab03f4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097191"
---
# <a name="cordebugiltonativemappingtypes-enumeration"></a><span data-ttu-id="b5aa5-102">Перечисление CorDebugIlToNativeMappingTypes</span><span class="sxs-lookup"><span data-stu-id="b5aa5-102">CorDebugIlToNativeMappingTypes Enumeration</span></span>
<span data-ttu-id="b5aa5-103">Указывает, соответствует ли определенный диапазон машинных инструкций, представленной экземпляром структуры COR_DEBUG_IL_TO_NATIVE_MAP, области кода.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-103">Indicates whether a particular range of native instructions, represented by an instance of the COR_DEBUG_IL_TO_NATIVE_MAP structure, corresponds to a special code region.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5aa5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5aa5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIlToNativeMappingTypes {  
    NO_MAPPING = -1,  
    PROLOG     = -2,  
    EPILOG     = -3  
} CorDebugIlToNativeMappingTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="b5aa5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b5aa5-105">Members</span></span>  
  
|<span data-ttu-id="b5aa5-106">Член</span><span class="sxs-lookup"><span data-stu-id="b5aa5-106">Member</span></span>|<span data-ttu-id="b5aa5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b5aa5-107">Description</span></span>|  
|------------|-----------------|  
|`NO_MAPPING`|<span data-ttu-id="b5aa5-108">Диапазон машинных инструкций не соответствует любой области кода.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-108">The range of native instructions does not correspond to any special code region.</span></span>|  
|`PROLOG`|<span data-ttu-id="b5aa5-109">Диапазон машинных инструкций соответствует пролога.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-109">The range of native instructions corresponds to the prolog.</span></span>|  
|`EPILOG`|<span data-ttu-id="b5aa5-110">Диапазон машинных инструкций соответствует эпилога.</span><span class="sxs-lookup"><span data-stu-id="b5aa5-110">The range of native instructions corresponds to the epilog.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5aa5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b5aa5-111">Requirements</span></span>  
 <span data-ttu-id="b5aa5-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5aa5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5aa5-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5aa5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5aa5-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5aa5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5aa5-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5aa5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5aa5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b5aa5-116">See also</span></span>

- [<span data-ttu-id="b5aa5-117">Метод GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="b5aa5-117">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="b5aa5-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="b5aa5-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
