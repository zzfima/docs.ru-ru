---
title: Интерфейс IMetaDataEmit2
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447914"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="d43cf-102">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d43cf-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="d43cf-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span><span class="sxs-lookup"><span data-stu-id="d43cf-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d43cf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d43cf-104">Methods</span></span>  
  
|<span data-ttu-id="d43cf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d43cf-105">Method</span></span>|<span data-ttu-id="d43cf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d43cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d43cf-107">Метод DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="d43cf-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="d43cf-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span><span class="sxs-lookup"><span data-stu-id="d43cf-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="d43cf-109">Метод DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="d43cf-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="d43cf-110">Creates a generic instance of a method, and gets a token to the definition.</span><span class="sxs-lookup"><span data-stu-id="d43cf-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="d43cf-111">Метод GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="d43cf-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="d43cf-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span><span class="sxs-lookup"><span data-stu-id="d43cf-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="d43cf-113">Метод ResetENCLog</span><span class="sxs-lookup"><span data-stu-id="d43cf-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="d43cf-114">Resets the edit-and-continue log and starts a new session.</span><span class="sxs-lookup"><span data-stu-id="d43cf-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="d43cf-115">Метод SaveDelta</span><span class="sxs-lookup"><span data-stu-id="d43cf-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="d43cf-116">Saves changes from the current edit-and-continue session to the specified file.</span><span class="sxs-lookup"><span data-stu-id="d43cf-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="d43cf-117">Метод SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="d43cf-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="d43cf-118">Saves changes from the current edit-and-continue session to memory.</span><span class="sxs-lookup"><span data-stu-id="d43cf-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="d43cf-119">Метод SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="d43cf-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="d43cf-120">Saves changes from the current edit-and-continue session to the specified stream.</span><span class="sxs-lookup"><span data-stu-id="d43cf-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="d43cf-121">Метод SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="d43cf-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="d43cf-122">Sets property values for the generic parameter definition referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="d43cf-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d43cf-123">Требования</span><span class="sxs-lookup"><span data-stu-id="d43cf-123">Requirements</span></span>  
 <span data-ttu-id="d43cf-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d43cf-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d43cf-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d43cf-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d43cf-126">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d43cf-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d43cf-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d43cf-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d43cf-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d43cf-128">See also</span></span>

- [<span data-ttu-id="d43cf-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="d43cf-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="d43cf-130">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d43cf-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
