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
ms.openlocfilehash: 1aa59ee559abff8006f0ac63a812e4315aa48154
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790312"
---
# <a name="variablelocationtype-enumeration"></a><span data-ttu-id="c5940-102">Перечисление VariableLocationType</span><span class="sxs-lookup"><span data-stu-id="c5940-102">VariableLocationType Enumeration</span></span>
<span data-ttu-id="c5940-103">Указывает тип собственного расположения переменной.</span><span class="sxs-lookup"><span data-stu-id="c5940-103">Indicates the native location type of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5940-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5940-104">Syntax</span></span>  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a><span data-ttu-id="c5940-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c5940-105">Members</span></span>  
  
|<span data-ttu-id="c5940-106">Член</span><span class="sxs-lookup"><span data-stu-id="c5940-106">Member</span></span>|<span data-ttu-id="c5940-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c5940-107">Description</span></span>|  
|------------|-----------------|  
|`VLT_REGISTER`|<span data-ttu-id="c5940-108">Переменная находится в регистре.</span><span class="sxs-lookup"><span data-stu-id="c5940-108">The variable is in a register.</span></span>|  
|`VLT_REGISTER_RELATIVE`|<span data-ttu-id="c5940-109">Переменная находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="c5940-109">The variable is in a register-relative memory location.</span></span>|  
|`VLT_INVALID`|<span data-ttu-id="c5940-110">Переменная не хранится в регистре или расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="c5940-110">The variable is not stored in a register or a register-relative memory location.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5940-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="c5940-111">Remarks</span></span>  
 <span data-ttu-id="c5940-112">Член перечисления `VariableLocationType` возвращается методом [ICorDebugVariableHome:: жетлокатионтипе](icordebugvariablehome-getlocationtype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c5940-112">A member of the `VariableLocationType` enumeration is returned by the [ICorDebugVariableHome::GetLocationType](icordebugvariablehome-getlocationtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5940-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c5940-113">Requirements</span></span>  
 <span data-ttu-id="c5940-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5940-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5940-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5940-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5940-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5940-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5940-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5940-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5940-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5940-118">See also</span></span>

- [<span data-ttu-id="c5940-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c5940-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
