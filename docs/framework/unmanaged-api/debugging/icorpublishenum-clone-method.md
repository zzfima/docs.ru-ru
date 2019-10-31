---
title: Метод ICorPublishEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: e9f7f1fc0f04e8cc8c69d533c1dbba380d04ebfb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140495"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="02113-102">Метод ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="02113-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="02113-103">Создает копию этого объекта [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="02113-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02113-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02113-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02113-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02113-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="02113-106">заполняет Указатель на адрес объекта `ICorPublishEnum`, который является копией этого `ICorPublishEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="02113-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02113-107">Требования</span><span class="sxs-lookup"><span data-stu-id="02113-107">Requirements</span></span>  
 <span data-ttu-id="02113-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02113-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02113-109">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="02113-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="02113-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02113-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02113-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02113-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02113-112">См. также</span><span class="sxs-lookup"><span data-stu-id="02113-112">See also</span></span>

- [<span data-ttu-id="02113-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="02113-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
