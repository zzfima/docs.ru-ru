---
title: "Структура COR_FIELD_OFFSET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD_OFFSET
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_FIELD_OFFSET
helpviewer_keywords: COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8e821a9d4ffa5054f687eff7360bc8d7cefb9f09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="3a465-102">Структура COR_FIELD_OFFSET</span><span class="sxs-lookup"><span data-stu-id="3a465-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="3a465-103">Хранит смещение указанного поля в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="3a465-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a465-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a465-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="3a465-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3a465-105">Members</span></span>  
  
|<span data-ttu-id="3a465-106">Член</span><span class="sxs-lookup"><span data-stu-id="3a465-106">Member</span></span>|<span data-ttu-id="3a465-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3a465-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="3a465-108">`mdFieldDef` Токен метаданных, представляющий поле.</span><span class="sxs-lookup"><span data-stu-id="3a465-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="3a465-109">Смещение поля внутри класса.</span><span class="sxs-lookup"><span data-stu-id="3a465-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a465-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a465-110">Remarks</span></span>  
 <span data-ttu-id="3a465-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) и [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) методы принимают параметр типа `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="3a465-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a465-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3a465-112">Requirements</span></span>  
 <span data-ttu-id="3a465-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a465-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a465-114">**Заголовок:** CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="3a465-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="3a465-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a465-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a465-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3a465-116">See Also</span></span>  
 [<span data-ttu-id="3a465-117">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="3a465-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="3a465-118">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3a465-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="3a465-119">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3a465-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
