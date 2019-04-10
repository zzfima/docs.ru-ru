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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dda284fc86f0a82472c59d6bab08fd4a87364723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225980"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="cbdc2-102">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="cbdc2-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="cbdc2-103">Предоставляет методы для создания новой области метаданных, или откройте существующий.</span><span class="sxs-lookup"><span data-stu-id="cbdc2-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cbdc2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cbdc2-104">Methods</span></span>  
  
|<span data-ttu-id="cbdc2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cbdc2-105">Method</span></span>|<span data-ttu-id="cbdc2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cbdc2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cbdc2-107">Метод DefineScope</span><span class="sxs-lookup"><span data-stu-id="cbdc2-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="cbdc2-108">Создает новую область в памяти, где можно создать новые метаданные.</span><span class="sxs-lookup"><span data-stu-id="cbdc2-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="cbdc2-109">Метод OpenScope</span><span class="sxs-lookup"><span data-stu-id="cbdc2-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="cbdc2-110">Открывает существующий файл на диске и сопоставляет его метаданные в память.</span><span class="sxs-lookup"><span data-stu-id="cbdc2-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="cbdc2-111">Метод OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="cbdc2-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="cbdc2-112">Откроется область памяти, содержащую существующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="cbdc2-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="cbdc2-113">То есть этот метод открывает указанную область памяти, в которой существующие данные интерпретируются как метаданные.</span><span class="sxs-lookup"><span data-stu-id="cbdc2-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbdc2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cbdc2-114">Requirements</span></span>  
 <span data-ttu-id="cbdc2-115">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbdc2-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbdc2-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cbdc2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbdc2-117">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cbdc2-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="cbdc2-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cbdc2-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cbdc2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="cbdc2-119">See also</span></span>

- [<span data-ttu-id="cbdc2-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="cbdc2-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="cbdc2-121">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="cbdc2-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
