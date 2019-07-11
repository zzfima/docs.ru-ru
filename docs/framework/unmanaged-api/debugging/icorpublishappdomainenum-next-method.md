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
ms.openlocfilehash: 38e4bd55a52cdbb3c242b8c3e5ff21f970b93ac0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765026"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="6acf9-102">Метод ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="6acf9-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="6acf9-103">Получает указанное число доменов приложений, которые в настоящее время существуют в процессе, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="6acf9-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acf9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6acf9-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6acf9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6acf9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6acf9-106">[in] Количество элементов для получения.</span><span class="sxs-lookup"><span data-stu-id="6acf9-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="6acf9-107">[out] Получить указатель на массив [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) объектов, каждый из которых представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="6acf9-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6acf9-108">[out] Указатель на количество фактически возвращенных доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="6acf9-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="6acf9-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="6acf9-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6acf9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6acf9-110">Requirements</span></span>  
 <span data-ttu-id="6acf9-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6acf9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6acf9-112">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6acf9-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6acf9-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6acf9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6acf9-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6acf9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acf9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6acf9-115">See also</span></span>

- [<span data-ttu-id="6acf9-116">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="6acf9-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
