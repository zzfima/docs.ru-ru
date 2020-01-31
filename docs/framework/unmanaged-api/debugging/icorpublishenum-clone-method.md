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
ms.openlocfilehash: afd16f1f31be9148422dd6d0be748036a8e5d99a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790662"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="cd33c-102">Метод ICorPublishEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="cd33c-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="cd33c-103">Создает копию этого объекта [ICorPublishEnum](icorpublishenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="cd33c-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd33c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd33c-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd33c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cd33c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="cd33c-106">заполняет Указатель на адрес объекта `ICorPublishEnum`, который является копией этого `ICorPublishEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="cd33c-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd33c-107">Требования</span><span class="sxs-lookup"><span data-stu-id="cd33c-107">Requirements</span></span>  
 <span data-ttu-id="cd33c-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd33c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd33c-109">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="cd33c-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cd33c-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd33c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd33c-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd33c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd33c-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd33c-112">See also</span></span>

- [<span data-ttu-id="cd33c-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="cd33c-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
