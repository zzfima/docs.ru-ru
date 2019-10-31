---
title: Метод ICorPublishAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: 0553d8b07e3a16dc31474b5470ba2dd8ba365cb2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140502"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="ebc9f-102">Метод ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ebc9f-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="ebc9f-103">Возвращает указанное количество доменов приложений, которые в данный момент существуют в процессе, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="ebc9f-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebc9f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebc9f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebc9f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ebc9f-106">окне Число извлекаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="ebc9f-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="ebc9f-107">заполняет Указатель на массив полученных объектов [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) , каждый из которых представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="ebc9f-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ebc9f-108">заполняет Указатель на число фактически возвращенных доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="ebc9f-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="ebc9f-109">Это значение может быть равно null, если `celt` является одним.</span><span class="sxs-lookup"><span data-stu-id="ebc9f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebc9f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ebc9f-110">Requirements</span></span>  
 <span data-ttu-id="ebc9f-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebc9f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc9f-112">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="ebc9f-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ebc9f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebc9f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebc9f-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc9f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc9f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ebc9f-115">See also</span></span>

- [<span data-ttu-id="ebc9f-116">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="ebc9f-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
