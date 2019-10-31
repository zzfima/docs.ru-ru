---
title: Метод ICorPublishAppDomain::GetID
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
ms.openlocfilehash: 33a72d9aea09f808d42d1a17a7ec5640d20d7c79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140375"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="b6439-102">Метод ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="b6439-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="b6439-103">Возвращает уникальный идентификатор для этого [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b6439-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6439-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6439-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6439-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6439-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="b6439-106">заполняет Указатель на идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="b6439-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6439-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="b6439-107">Remarks</span></span>  
 <span data-ttu-id="b6439-108">Идентификатор уникален только в области содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="b6439-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6439-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b6439-109">Requirements</span></span>  
 <span data-ttu-id="b6439-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6439-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6439-111">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="b6439-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b6439-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6439-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6439-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6439-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6439-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b6439-114">See also</span></span>

- [<span data-ttu-id="b6439-115">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="b6439-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
