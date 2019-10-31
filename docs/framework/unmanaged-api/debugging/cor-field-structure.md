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
ms.openlocfilehash: 78e34d9d33d34047e3ebd2effb4894bc7b709585
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132361"
---
# <a name="cor_field-structure"></a><span data-ttu-id="2d36d-102">Структура COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="2d36d-102">COR_FIELD Structure</span></span>
<span data-ttu-id="2d36d-103">Предоставляет сведения о поле в объекте.</span><span class="sxs-lookup"><span data-stu-id="2d36d-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d36d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d36d-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="2d36d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="2d36d-105">Members</span></span>  
  
|<span data-ttu-id="2d36d-106">Член</span><span class="sxs-lookup"><span data-stu-id="2d36d-106">Member</span></span>|<span data-ttu-id="2d36d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2d36d-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="2d36d-108">Токен `mdFieldDef`, который можно использовать для получения сведений о полях.</span><span class="sxs-lookup"><span data-stu-id="2d36d-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="2d36d-109">Смещение в байтах для данных поля в объекте.</span><span class="sxs-lookup"><span data-stu-id="2d36d-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="2d36d-110">Значение [COR_TYPEID](cor-typeid-structure.md) , определяющее тип этого поля.</span><span class="sxs-lookup"><span data-stu-id="2d36d-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="2d36d-111">Значение перечисления Корелементтипе, указывающее тип поля.</span><span class="sxs-lookup"><span data-stu-id="2d36d-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d36d-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="2d36d-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d36d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2d36d-113">Requirements</span></span>  
 <span data-ttu-id="2d36d-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d36d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d36d-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d36d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d36d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d36d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d36d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d36d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d36d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2d36d-118">See also</span></span>

- [<span data-ttu-id="2d36d-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="2d36d-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="2d36d-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="2d36d-120">Debugging</span></span>](index.md)
