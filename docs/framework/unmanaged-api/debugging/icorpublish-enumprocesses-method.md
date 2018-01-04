---
title: "Метод ICorPublish::EnumProcesses"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.EnumProcesses
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7e0af492cbec401d7470502de807033f21e39f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="84b30-102">Метод ICorPublish::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="84b30-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="84b30-103">Возвращает перечислитель для управляемых процессов, запущенных на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="84b30-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84b30-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84b30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84b30-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="84b30-106">Значение [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) перечисление, указывающее тип процесса требуется получить.</span><span class="sxs-lookup"><span data-stu-id="84b30-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="84b30-107">В текущей версии допускается только COR_PUB_MANAGEDONLY.</span><span class="sxs-lookup"><span data-stu-id="84b30-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="84b30-108">Указатель на адрес [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) экземпляр, который является перечислителем процессов.</span><span class="sxs-lookup"><span data-stu-id="84b30-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84b30-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="84b30-109">Remarks</span></span>  
 <span data-ttu-id="84b30-110">Коллекция процессов перечислителя на основе моментального снимка процессов, которые выполняются при `EnumProcesses` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="84b30-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="84b30-111">Перечислитель не будет содержать все процессы, завершение перед или после запуска `EnumProcesses` вызывается.</span><span class="sxs-lookup"><span data-stu-id="84b30-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="84b30-112">`EnumProcesses` Метод может вызываться несколько раз в данном [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) экземпляра для создания новой актуальной коллекции процессов.</span><span class="sxs-lookup"><span data-stu-id="84b30-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="84b30-113">Существующие коллекции не будут затронуты, последующие вызовы `EnumProcesses` метод.</span><span class="sxs-lookup"><span data-stu-id="84b30-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84b30-114">Требования</span><span class="sxs-lookup"><span data-stu-id="84b30-114">Requirements</span></span>  
 <span data-ttu-id="84b30-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84b30-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84b30-116">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="84b30-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="84b30-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84b30-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84b30-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84b30-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b30-119">См. также</span><span class="sxs-lookup"><span data-stu-id="84b30-119">See Also</span></span>  
 [<span data-ttu-id="84b30-120">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="84b30-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
