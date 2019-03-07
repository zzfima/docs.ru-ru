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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e36d48c3747c2d74f4c7f47268219283b07c9a39
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500203"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="58dfb-102">Метод ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="58dfb-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="58dfb-103">Получает указанное число доменов приложений, которые в настоящее время существуют в процессе, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="58dfb-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58dfb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="58dfb-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58dfb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="58dfb-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="58dfb-106">[in] Количество элементов для получения.</span><span class="sxs-lookup"><span data-stu-id="58dfb-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="58dfb-107">[out] Получить указатель на массив [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) объектов, каждый из которых представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="58dfb-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="58dfb-108">[out] Указатель на количество фактически возвращенных доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="58dfb-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="58dfb-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="58dfb-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58dfb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="58dfb-110">Requirements</span></span>  
 <span data-ttu-id="58dfb-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58dfb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58dfb-112">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="58dfb-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="58dfb-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58dfb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58dfb-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58dfb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58dfb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="58dfb-115">See also</span></span>
- [<span data-ttu-id="58dfb-116">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="58dfb-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
