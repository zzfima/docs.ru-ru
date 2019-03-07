---
title: Метод ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77bae0de732fc8847650b9ce03f8228111a76334
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466522"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="c2d36-102">Метод ICorPublish::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="c2d36-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="c2d36-103">Возвращает перечислитель для управляемых процессов, запущенных на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="c2d36-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d36-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2d36-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2d36-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2d36-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="c2d36-106">Значение [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) перечисление, указывающее тип процесса требуется получить.</span><span class="sxs-lookup"><span data-stu-id="c2d36-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="c2d36-107">В текущей версии только COR_PUB_MANAGEDONLY является допустимым.</span><span class="sxs-lookup"><span data-stu-id="c2d36-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="c2d36-108">Указатель на адрес [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) экземпляр, который является перечислителем процессов.</span><span class="sxs-lookup"><span data-stu-id="c2d36-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2d36-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2d36-109">Remarks</span></span>  
 <span data-ttu-id="c2d36-110">Перечислитель коллекции процессов основан на моментальный снимок процессов, которые выполняются при `EnumProcesses` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="c2d36-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="c2d36-111">Перечислитель не будет включать все процессы, прежде чем или запустить после `EnumProcesses` вызывается.</span><span class="sxs-lookup"><span data-stu-id="c2d36-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="c2d36-112">`EnumProcesses` Метод может вызываться несколько раз на этом [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) экземпляра для создания новой актуальной коллекции процессов.</span><span class="sxs-lookup"><span data-stu-id="c2d36-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="c2d36-113">Существующие коллекции не будут затронуты, последующие вызовы `EnumProcesses` метод.</span><span class="sxs-lookup"><span data-stu-id="c2d36-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2d36-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c2d36-114">Requirements</span></span>  
 <span data-ttu-id="c2d36-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2d36-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2d36-116">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c2d36-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c2d36-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2d36-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2d36-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d36-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d36-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d36-119">See also</span></span>
- [<span data-ttu-id="c2d36-120">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="c2d36-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
