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
ms.openlocfilehash: 6f7f400c51ded0b98c0c2286cb6f90bbd77e47d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178402"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="1ffd8-102">Метод ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="1ffd8-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="1ffd8-103">Получает указанное количество доменов приложений, которые в настоящее время существуют в процессе, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="1ffd8-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ffd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ffd8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ffd8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ffd8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1ffd8-106">(в) Количество элементов, которые необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="1ffd8-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="1ffd8-107">(ваут) Указатель на массив извлеченных объектов [ICorPublishAppDomain,](icorpublishappdomain-interface.md) каждый из которых представляет собой домен приложения.</span><span class="sxs-lookup"><span data-stu-id="1ffd8-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1ffd8-108">(ваут) Указатель на количество доменов приложений фактически вернулся.</span><span class="sxs-lookup"><span data-stu-id="1ffd8-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="1ffd8-109">Это значение может `celt` быть нулевым, если он один.</span><span class="sxs-lookup"><span data-stu-id="1ffd8-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ffd8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1ffd8-110">Requirements</span></span>  
 <span data-ttu-id="1ffd8-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ffd8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ffd8-112">**Заголовок:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1ffd8-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1ffd8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ffd8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ffd8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ffd8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ffd8-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ffd8-115">See also</span></span>

- [<span data-ttu-id="1ffd8-116">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="1ffd8-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
