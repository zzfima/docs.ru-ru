---
title: Структура COR_FIELD
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d570f9392bbd66f0d9031c776b139ee3b30541b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698223"
---
# <a name="corfield-structure"></a><span data-ttu-id="9b398-102">Структура COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="9b398-102">COR_FIELD Structure</span></span>
<span data-ttu-id="9b398-103">Предоставляет сведения о поле в объекте.</span><span class="sxs-lookup"><span data-stu-id="9b398-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b398-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b398-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="9b398-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9b398-105">Members</span></span>  
  
|<span data-ttu-id="9b398-106">Член</span><span class="sxs-lookup"><span data-stu-id="9b398-106">Member</span></span>|<span data-ttu-id="9b398-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="9b398-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="9b398-108">`mdFieldDef` Токен, который может использоваться для получения сведений о поле.</span><span class="sxs-lookup"><span data-stu-id="9b398-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="9b398-109">Смещение в байтах к данным поля в объекте.</span><span class="sxs-lookup"><span data-stu-id="9b398-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="9b398-110">Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) значение, определяющее тип этого поля.</span><span class="sxs-lookup"><span data-stu-id="9b398-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="9b398-111">CorElementType значение перечисления, указывающее тип поля.</span><span class="sxs-lookup"><span data-stu-id="9b398-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b398-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b398-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b398-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9b398-113">Requirements</span></span>  
 <span data-ttu-id="9b398-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b398-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b398-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b398-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b398-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b398-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b398-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b398-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b398-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9b398-118">See also</span></span>
- [<span data-ttu-id="9b398-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="9b398-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="9b398-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="9b398-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
