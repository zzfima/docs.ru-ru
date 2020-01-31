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
ms.openlocfilehash: 4799c1d04e8172c604eeec50f2b841a6db063949
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790585"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="76f85-102">Метод ICorPublishProcess::EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="76f85-102">ICorPublishProcess::EnumAppDomains Method</span></span>
<span data-ttu-id="76f85-103">Возвращает перечислитель для доменов приложений в процессе, на который ссылается этот [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="76f85-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76f85-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76f85-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="76f85-106">заполняет Указатель на адрес экземпляра [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) , который позволяет выполнять итерацию по коллекции доменов приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="76f85-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76f85-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="76f85-107">Remarks</span></span>  
 <span data-ttu-id="76f85-108">Список доменов приложений основан на моментальном снимке доменов приложений, существующих при вызове метода `EnumAppDomains`.</span><span class="sxs-lookup"><span data-stu-id="76f85-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="76f85-109">Этот метод может быть вызван более одного раза для создания нового списка обновлений.</span><span class="sxs-lookup"><span data-stu-id="76f85-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="76f85-110">Последующие вызовы этого метода не будут затронуты существующими списками.</span><span class="sxs-lookup"><span data-stu-id="76f85-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="76f85-111">Если процесс был завершен, `EnumAppDomains` завершится ошибкой со значением HRESULT CORDBG_E_PROCESS_TERMINATED.</span><span class="sxs-lookup"><span data-stu-id="76f85-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76f85-112">Требования</span><span class="sxs-lookup"><span data-stu-id="76f85-112">Requirements</span></span>  
 <span data-ttu-id="76f85-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76f85-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f85-114">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="76f85-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="76f85-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76f85-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76f85-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76f85-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f85-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="76f85-117">See also</span></span>

- [<span data-ttu-id="76f85-118">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="76f85-118">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
