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
ms.openlocfilehash: 646952d5cd55b74081a0ba6171a6eee6b0138512
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443964"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="1bfa3-102">Структура COR_FIELD_OFFSET</span><span class="sxs-lookup"><span data-stu-id="1bfa3-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="1bfa3-103">Хранит смещение указанного поля в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="1bfa3-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bfa3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bfa3-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="1bfa3-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1bfa3-105">Members</span></span>  
  
|<span data-ttu-id="1bfa3-106">Член</span><span class="sxs-lookup"><span data-stu-id="1bfa3-106">Member</span></span>|<span data-ttu-id="1bfa3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1bfa3-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="1bfa3-108">`mdFieldDef`ный маркер метаданных, представляющий поле.</span><span class="sxs-lookup"><span data-stu-id="1bfa3-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="1bfa3-109">Смещение поля в его классе.</span><span class="sxs-lookup"><span data-stu-id="1bfa3-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bfa3-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1bfa3-110">Remarks</span></span>  
 <span data-ttu-id="1bfa3-111">Методы [IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) и [IMetaDataEmit:: сеткласслайаут](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) принимают параметр типа `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="1bfa3-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bfa3-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1bfa3-112">Requirements</span></span>  
 <span data-ttu-id="1bfa3-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bfa3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bfa3-114">**Заголовок:** Корхдр. h, CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="1bfa3-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="1bfa3-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bfa3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfa3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1bfa3-116">See also</span></span>

- [<span data-ttu-id="1bfa3-117">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="1bfa3-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="1bfa3-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1bfa3-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1bfa3-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1bfa3-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
