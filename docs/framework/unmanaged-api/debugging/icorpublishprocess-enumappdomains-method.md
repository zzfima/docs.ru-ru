---
title: "Метод ICorPublishProcess::EnumAppDomains"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.EnumAppDomains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 938c022788d5ed9f0e28f794432017748dc096e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="b56d3-102">Метод ICorPublishProcess::EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="b56d3-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="b56d3-103">Возвращает перечислитель для доменов приложений в процессе, на который ссылается это [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b56d3-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b56d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b56d3-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b56d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b56d3-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b56d3-106">[out] Указатель на адрес [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) экземпляра, позволяющий выполнять итерацию по коллекции доменов приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="b56d3-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b56d3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b56d3-107">Remarks</span></span>  
 <span data-ttu-id="b56d3-108">Список доменов приложений на основе моментального снимка доменов приложений, которые существуют при `EnumAppDomains` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="b56d3-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="b56d3-109">Этот метод может вызываться несколько раз для создания нового актуального списка.</span><span class="sxs-lookup"><span data-stu-id="b56d3-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="b56d3-110">Существующие списки не повлияет на последующие вызовы этого метода.</span><span class="sxs-lookup"><span data-stu-id="b56d3-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="b56d3-111">Если процесс был завершен, `EnumAppDomains` со значением HRESULT CORDBG_E_PROCESS_TERMINATED не удастся.</span><span class="sxs-lookup"><span data-stu-id="b56d3-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b56d3-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b56d3-112">Requirements</span></span>  
 <span data-ttu-id="b56d3-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b56d3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b56d3-114">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="b56d3-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b56d3-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b56d3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b56d3-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b56d3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b56d3-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b56d3-117">See Also</span></span>  
 [<span data-ttu-id="b56d3-118">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="b56d3-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
