---
title: "Интерфейс ICLRMetadataLocator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetadataLocator
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRMetadataLocator
helpviewer_keywords: ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a06997c47a85ced56dc579759192f7256def4f5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="950eb-102">Интерфейс ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="950eb-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="950eb-103">Используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="950eb-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="950eb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="950eb-104">Methods</span></span>  
  
|<span data-ttu-id="950eb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="950eb-105">Method</span></span>|<span data-ttu-id="950eb-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="950eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="950eb-107">Метод GetMetadata</span><span class="sxs-lookup"><span data-stu-id="950eb-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="950eb-108">Извлекает метаданные образа из целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="950eb-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="950eb-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="950eb-109">Remarks</span></span>  
 <span data-ttu-id="950eb-110">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="950eb-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="950eb-111">Например реализация активного процесса будет отличаться от дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="950eb-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="950eb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="950eb-112">Requirements</span></span>  
 <span data-ttu-id="950eb-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="950eb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="950eb-114">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="950eb-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="950eb-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="950eb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="950eb-116">**.**</span><span class="sxs-lookup"><span data-stu-id="950eb-116">**.**</span></span> <span data-ttu-id="950eb-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="950eb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="950eb-118">См. также</span><span class="sxs-lookup"><span data-stu-id="950eb-118">See Also</span></span>  
 [<span data-ttu-id="950eb-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="950eb-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
