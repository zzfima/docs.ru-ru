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
ms.openlocfilehash: 1cc7a299e6be328095c0368acf0a4b767fb74d01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423953"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="95eb5-102">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="95eb5-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="95eb5-103">Указывает тип собственного расположение переменной.</span><span class="sxs-lookup"><span data-stu-id="95eb5-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95eb5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95eb5-104">Syntax</span></span>  
  
```  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="95eb5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="95eb5-105">Members</span></span>  
  
|<span data-ttu-id="95eb5-106">Член</span><span class="sxs-lookup"><span data-stu-id="95eb5-106">Member</span></span>|<span data-ttu-id="95eb5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="95eb5-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="95eb5-108">Переменная находится в регистре.</span><span class="sxs-lookup"><span data-stu-id="95eb5-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="95eb5-109">Переменная находится в расположении относительно регистра памяти.</span><span class="sxs-lookup"><span data-stu-id="95eb5-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="95eb5-110">Переменная не хранятся в регистрах или в расположении относительно регистра памяти.</span><span class="sxs-lookup"><span data-stu-id="95eb5-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95eb5-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="95eb5-111">Remarks</span></span>  
 <span data-ttu-id="95eb5-112">Член `VariableLocationType` возвращается перечисления [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="95eb5-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95eb5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="95eb5-113">Requirements</span></span>  
 <span data-ttu-id="95eb5-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95eb5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95eb5-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95eb5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95eb5-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95eb5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95eb5-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95eb5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95eb5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="95eb5-118">See Also</span></span>  
 [<span data-ttu-id="95eb5-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="95eb5-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
