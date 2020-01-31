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
ms.openlocfilehash: 8d6e130981693268ae5c2cd615036b84ca8ed2d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790697"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="5f400-102">Метод ICorPublishAppDomain::GetID</span><span class="sxs-lookup"><span data-stu-id="5f400-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="5f400-103">Возвращает уникальный идентификатор для этого [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5f400-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f400-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f400-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f400-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f400-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="5f400-106">заполняет Указатель на идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="5f400-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f400-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="5f400-107">Remarks</span></span>  
 <span data-ttu-id="5f400-108">Идентификатор уникален только в области содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="5f400-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f400-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5f400-109">Requirements</span></span>  
 <span data-ttu-id="5f400-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f400-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f400-111">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="5f400-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5f400-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f400-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f400-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f400-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f400-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f400-114">See also</span></span>

- [<span data-ttu-id="5f400-115">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="5f400-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
