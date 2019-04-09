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
ms.openlocfilehash: 392254efcd099aca60e58b3cc0bc61ca85aa2c66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099954"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="5d40b-102">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="5d40b-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="5d40b-103">Указывает тип собственного расположение переменной.</span><span class="sxs-lookup"><span data-stu-id="5d40b-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d40b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d40b-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="5d40b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5d40b-105">Members</span></span>  
  
|<span data-ttu-id="5d40b-106">Член</span><span class="sxs-lookup"><span data-stu-id="5d40b-106">Member</span></span>|<span data-ttu-id="5d40b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5d40b-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="5d40b-108">Переменная находится в регистре.</span><span class="sxs-lookup"><span data-stu-id="5d40b-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="5d40b-109">Переменная находится в расположении памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="5d40b-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="5d40b-110">Переменная не хранится в регистр и в памяти зависящий от регистра.</span><span class="sxs-lookup"><span data-stu-id="5d40b-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d40b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d40b-111">Remarks</span></span>  
 <span data-ttu-id="5d40b-112">Является членом `VariableLocationType` возвращенного перечисления [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="5d40b-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d40b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5d40b-113">Requirements</span></span>  
 <span data-ttu-id="5d40b-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d40b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d40b-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d40b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d40b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d40b-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5d40b-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5d40b-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d40b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5d40b-118">See also</span></span>

- [<span data-ttu-id="5d40b-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="5d40b-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
