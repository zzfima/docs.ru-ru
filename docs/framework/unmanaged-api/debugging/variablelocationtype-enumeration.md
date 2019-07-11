---
title: Перечисление VariableLocationType
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2093466c78b039a06a01e2d850b88ff4543d0ab3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752455"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="71665-102">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="71665-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="71665-103">Указывает тип собственного расположение переменной.</span><span class="sxs-lookup"><span data-stu-id="71665-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71665-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71665-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="71665-105">Участники</span><span class="sxs-lookup"><span data-stu-id="71665-105">Members</span></span>  
  
|<span data-ttu-id="71665-106">Член</span><span class="sxs-lookup"><span data-stu-id="71665-106">Member</span></span>|<span data-ttu-id="71665-107">Описание</span><span class="sxs-lookup"><span data-stu-id="71665-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="71665-108">Переменная находится в регистре.</span><span class="sxs-lookup"><span data-stu-id="71665-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="71665-109">Переменная находится в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="71665-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="71665-110">Переменная не хранится в регистр и в памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="71665-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71665-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="71665-111">Remarks</span></span>  
 <span data-ttu-id="71665-112">Является членом `VariableLocationType` возвращенного перечисления [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="71665-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71665-113">Требования</span><span class="sxs-lookup"><span data-stu-id="71665-113">Requirements</span></span>  
 <span data-ttu-id="71665-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71665-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71665-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71665-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71665-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71665-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71665-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71665-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71665-118">См. также</span><span class="sxs-lookup"><span data-stu-id="71665-118">See also</span></span>

- [<span data-ttu-id="71665-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="71665-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
