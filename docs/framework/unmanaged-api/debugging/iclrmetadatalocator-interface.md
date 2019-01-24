---
title: Интерфейс ICLRMetadataLocator
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d1d767de88b239c96cb98130b6ff006e3f75b09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495036"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="7c235-102">Интерфейс ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="7c235-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="7c235-103">Используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="7c235-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c235-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7c235-104">Methods</span></span>  
  
|<span data-ttu-id="7c235-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7c235-105">Method</span></span>|<span data-ttu-id="7c235-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="7c235-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c235-107">Метод GetMetadata</span><span class="sxs-lookup"><span data-stu-id="7c235-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="7c235-108">Извлекает метаданные изображения из целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="7c235-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c235-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c235-109">Remarks</span></span>  
 <span data-ttu-id="7c235-110">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="7c235-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="7c235-111">Например реализация активного процесса будет отличаться от дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="7c235-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c235-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7c235-112">Requirements</span></span>  
 <span data-ttu-id="7c235-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c235-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c235-114">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7c235-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7c235-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c235-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c235-116">**.**</span><span class="sxs-lookup"><span data-stu-id="7c235-116">**.**</span></span> <span data-ttu-id="7c235-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c235-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c235-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7c235-118">See also</span></span>
- [<span data-ttu-id="7c235-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7c235-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
