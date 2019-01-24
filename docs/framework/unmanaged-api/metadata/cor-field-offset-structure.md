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
ms.openlocfilehash: 98a58c5e686a0650fa62752f6d1d50706d58e8d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698665"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="780de-102">Структура COR_FIELD_OFFSET</span><span class="sxs-lookup"><span data-stu-id="780de-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="780de-103">Хранит смещение указанного поля в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="780de-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="780de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="780de-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="780de-105">Участники</span><span class="sxs-lookup"><span data-stu-id="780de-105">Members</span></span>  
  
|<span data-ttu-id="780de-106">Член</span><span class="sxs-lookup"><span data-stu-id="780de-106">Member</span></span>|<span data-ttu-id="780de-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="780de-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="780de-108">`mdFieldDef` Токен метаданных, представляющий поле.</span><span class="sxs-lookup"><span data-stu-id="780de-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="780de-109">Смещение поля внутри класса.</span><span class="sxs-lookup"><span data-stu-id="780de-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="780de-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="780de-110">Remarks</span></span>  
 <span data-ttu-id="780de-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) и [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) методы принимают параметр типа `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="780de-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="780de-112">Требования</span><span class="sxs-lookup"><span data-stu-id="780de-112">Requirements</span></span>  
 <span data-ttu-id="780de-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="780de-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="780de-114">**Заголовок.** CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="780de-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="780de-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="780de-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="780de-116">См. также</span><span class="sxs-lookup"><span data-stu-id="780de-116">See also</span></span>
- [<span data-ttu-id="780de-117">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="780de-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="780de-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="780de-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="780de-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="780de-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
