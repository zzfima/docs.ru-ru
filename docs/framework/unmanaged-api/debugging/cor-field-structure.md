---
title: "Структура COR_FIELD"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_FIELD
helpviewer_keywords: COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a01687b5a49bb64ab037dc408c8cc5bd381be589
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="corfield-structure"></a><span data-ttu-id="beae8-102">Структура COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="beae8-102">COR_FIELD Structure</span></span>
<span data-ttu-id="beae8-103">Предоставляет сведения о поле в объекте.</span><span class="sxs-lookup"><span data-stu-id="beae8-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beae8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beae8-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="beae8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="beae8-105">Members</span></span>  
  
|<span data-ttu-id="beae8-106">Член</span><span class="sxs-lookup"><span data-stu-id="beae8-106">Member</span></span>|<span data-ttu-id="beae8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="beae8-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="beae8-108">`mdFieldDef` Маркер, который может использоваться для получения сведений о поле.</span><span class="sxs-lookup"><span data-stu-id="beae8-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="beae8-109">Смещение в байтах данных поля в объекте.</span><span class="sxs-lookup"><span data-stu-id="beae8-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="beae8-110">Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) значение, определяющее тип этого поля.</span><span class="sxs-lookup"><span data-stu-id="beae8-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="beae8-111">Значение CorElementType перечисление, указывающее тип поля.</span><span class="sxs-lookup"><span data-stu-id="beae8-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beae8-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="beae8-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beae8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="beae8-113">Requirements</span></span>  
 <span data-ttu-id="beae8-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beae8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beae8-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="beae8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="beae8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="beae8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="beae8-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beae8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beae8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="beae8-118">See Also</span></span>  
 [<span data-ttu-id="beae8-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="beae8-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="beae8-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="beae8-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
