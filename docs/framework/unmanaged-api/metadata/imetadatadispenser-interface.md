---
title: Интерфейс IMetaDataDispenser
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: b7ce76c22e7188117bddd9e4f328e323f6742685
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436228"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="70a37-102">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="70a37-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="70a37-103">Provides methods to create a new metadata scope, or open an existing one.</span><span class="sxs-lookup"><span data-stu-id="70a37-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70a37-104">Методы</span><span class="sxs-lookup"><span data-stu-id="70a37-104">Methods</span></span>  
  
|<span data-ttu-id="70a37-105">Метод</span><span class="sxs-lookup"><span data-stu-id="70a37-105">Method</span></span>|<span data-ttu-id="70a37-106">Описание</span><span class="sxs-lookup"><span data-stu-id="70a37-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70a37-107">Метод DefineScope</span><span class="sxs-lookup"><span data-stu-id="70a37-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="70a37-108">Creates a new area in memory where you can create new metadata.</span><span class="sxs-lookup"><span data-stu-id="70a37-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="70a37-109">Метод OpenScope</span><span class="sxs-lookup"><span data-stu-id="70a37-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="70a37-110">Opens an existing, on-disk file and maps its metadata into memory.</span><span class="sxs-lookup"><span data-stu-id="70a37-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="70a37-111">Метод OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="70a37-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="70a37-112">Opens an area of memory that contains existing metadata.</span><span class="sxs-lookup"><span data-stu-id="70a37-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="70a37-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span><span class="sxs-lookup"><span data-stu-id="70a37-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70a37-114">Требования</span><span class="sxs-lookup"><span data-stu-id="70a37-114">Requirements</span></span>  
 <span data-ttu-id="70a37-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70a37-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70a37-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="70a37-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70a37-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70a37-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70a37-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70a37-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70a37-119">См. также</span><span class="sxs-lookup"><span data-stu-id="70a37-119">See also</span></span>

- [<span data-ttu-id="70a37-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="70a37-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="70a37-121">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="70a37-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
