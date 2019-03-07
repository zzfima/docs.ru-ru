---
title: Метод ICorPublishProcess::EnumAppDomains
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c938adb518fe8c2bd7ac59fe47d7cd2a4f6df886
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492768"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="f9607-102">Метод ICorPublishProcess::EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="f9607-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="f9607-103">Возвращает перечислитель для доменов приложений в процессе, который ссылается этот [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f9607-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9607-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9607-104">Syntax</span></span>  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9607-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9607-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f9607-106">[out] Указатель на адрес [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) экземпляра, позволяющий выполнять итерацию по коллекции доменов приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="f9607-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9607-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9607-107">Remarks</span></span>  
 <span data-ttu-id="f9607-108">Список доменов приложений зависит от моментального снимка доменов приложений, которые существуют при `EnumAppDomains` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="f9607-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="f9607-109">Этот метод может вызываться несколько раз для создания нового актуального списка.</span><span class="sxs-lookup"><span data-stu-id="f9607-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="f9607-110">Существующие списки не будут применяться последующие вызовы этого метода.</span><span class="sxs-lookup"><span data-stu-id="f9607-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="f9607-111">Если процесс был завершен, `EnumAppDomains` со значением HRESULT CORDBG_E_PROCESS_TERMINATED не удастся.</span><span class="sxs-lookup"><span data-stu-id="f9607-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9607-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f9607-112">Requirements</span></span>  
 <span data-ttu-id="f9607-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9607-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9607-114">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f9607-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f9607-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9607-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9607-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9607-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9607-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f9607-117">See also</span></span>
- [<span data-ttu-id="f9607-118">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="f9607-118">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
