---
title: Структура COR_FIELD_OFFSET
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfbb22d231d16be7757ff5df26a5a010928af54
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767064"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="6f13b-102">Структура COR_FIELD_OFFSET</span><span class="sxs-lookup"><span data-stu-id="6f13b-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="6f13b-103">Хранит смещение указанного поля в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="6f13b-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f13b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f13b-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="6f13b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6f13b-105">Members</span></span>  
  
|<span data-ttu-id="6f13b-106">Член</span><span class="sxs-lookup"><span data-stu-id="6f13b-106">Member</span></span>|<span data-ttu-id="6f13b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6f13b-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="6f13b-108">`mdFieldDef` Токен метаданных, представляющий поле.</span><span class="sxs-lookup"><span data-stu-id="6f13b-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="6f13b-109">Смещение поля внутри класса.</span><span class="sxs-lookup"><span data-stu-id="6f13b-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f13b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f13b-110">Remarks</span></span>  
 <span data-ttu-id="6f13b-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) и [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) методы принимают параметр типа `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="6f13b-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f13b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6f13b-112">Requirements</span></span>  
 <span data-ttu-id="6f13b-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f13b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f13b-114">**Заголовок.** CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="6f13b-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="6f13b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f13b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f13b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6f13b-116">See also</span></span>

- [<span data-ttu-id="6f13b-117">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="6f13b-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="6f13b-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6f13b-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6f13b-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6f13b-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
