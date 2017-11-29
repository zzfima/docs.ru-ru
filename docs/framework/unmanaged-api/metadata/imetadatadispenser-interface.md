---
title: "Интерфейс IMetaDataDispenser"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser
helpviewer_keywords: IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5a0464f2fb7b81d98fcbb4b04bc465cf57b1b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="62988-102">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="62988-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="62988-103">Предоставляет методы для создания новой области метаданных или откройте существующий.</span><span class="sxs-lookup"><span data-stu-id="62988-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62988-104">Методы</span><span class="sxs-lookup"><span data-stu-id="62988-104">Methods</span></span>  
  
|<span data-ttu-id="62988-105">Метод</span><span class="sxs-lookup"><span data-stu-id="62988-105">Method</span></span>|<span data-ttu-id="62988-106">Описание</span><span class="sxs-lookup"><span data-stu-id="62988-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62988-107">Метод DefineScope</span><span class="sxs-lookup"><span data-stu-id="62988-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="62988-108">Создает новую область в памяти, где можно создать новые метаданные.</span><span class="sxs-lookup"><span data-stu-id="62988-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="62988-109">Метод OpenScope</span><span class="sxs-lookup"><span data-stu-id="62988-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="62988-110">Открывает существующий файл на диске и сопоставляет его метаданные в память.</span><span class="sxs-lookup"><span data-stu-id="62988-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="62988-111">Метод OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="62988-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="62988-112">Открывает область памяти, содержащую существующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="62988-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="62988-113">То есть этот метод открывает заданную область памяти, в которой существующие данные интерпретируются как метаданные.</span><span class="sxs-lookup"><span data-stu-id="62988-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62988-114">Требования</span><span class="sxs-lookup"><span data-stu-id="62988-114">Requirements</span></span>  
 <span data-ttu-id="62988-115">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62988-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62988-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="62988-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62988-117">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62988-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62988-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62988-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62988-119">См. также</span><span class="sxs-lookup"><span data-stu-id="62988-119">See Also</span></span>  
 [<span data-ttu-id="62988-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="62988-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="62988-121">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="62988-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
