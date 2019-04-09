---
title: Структура COR_TYPE_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7efb2c3e8033b8bd8fa736a29b2ab9b3bedebeaa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109646"
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="08829-102">Структура COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="08829-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="08829-103">Предоставляет сведения о расположении объекта в памяти.</span><span class="sxs-lookup"><span data-stu-id="08829-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08829-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08829-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="08829-105">Участники</span><span class="sxs-lookup"><span data-stu-id="08829-105">Members</span></span>  
  
|<span data-ttu-id="08829-106">Член</span><span class="sxs-lookup"><span data-stu-id="08829-106">Member</span></span>|<span data-ttu-id="08829-107">Описание</span><span class="sxs-lookup"><span data-stu-id="08829-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="08829-108">Идентификатор родительского типа к этому типу.</span><span class="sxs-lookup"><span data-stu-id="08829-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="08829-109">Это будет идентификатор типа NULL (токен1 = 0, токен2 = 0), если идентификатор типа соответствует <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08829-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="08829-110">Размер базового объекта этого типа.</span><span class="sxs-lookup"><span data-stu-id="08829-110">The base size of an object of this type.</span></span> <span data-ttu-id="08829-111">Это общий размер для размера объектов, не являющийся переменной.</span><span class="sxs-lookup"><span data-stu-id="08829-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="08829-112">Число полей, включенных в объекты этого типа.</span><span class="sxs-lookup"><span data-stu-id="08829-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="08829-113">Если этот тип упаковывается, начало смещения полей объекта.</span><span class="sxs-lookup"><span data-stu-id="08829-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="08829-114">Это поле является допустимым только для типов значений, таких как примитивы и структуры.</span><span class="sxs-lookup"><span data-stu-id="08829-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="08829-115">CorElementType, к которой принадлежит этот тип.</span><span class="sxs-lookup"><span data-stu-id="08829-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08829-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="08829-116">Remarks</span></span>  
 <span data-ttu-id="08829-117">Если `numFields` больше нуля, можно вызвать [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) метод, чтобы получить сведения о полях в этом типе.</span><span class="sxs-lookup"><span data-stu-id="08829-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="08829-118">Если `type` — `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, или `ELEMENT_TYPE_SZARRAY`, размер объектов этого типа является переменной, и вы можете передать [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) структуру [ICorDebugProcess5::GetArrayLayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="08829-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08829-119">Требования</span><span class="sxs-lookup"><span data-stu-id="08829-119">Requirements</span></span>  
 <span data-ttu-id="08829-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08829-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08829-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08829-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08829-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08829-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="08829-123">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="08829-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08829-124">См. также</span><span class="sxs-lookup"><span data-stu-id="08829-124">See also</span></span>

- [<span data-ttu-id="08829-125">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="08829-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="08829-126">Отладка</span><span class="sxs-lookup"><span data-stu-id="08829-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
