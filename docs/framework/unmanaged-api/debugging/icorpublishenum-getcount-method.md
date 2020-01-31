---
title: Метод ICorPublishEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: 0b3754fbcca50b52039dc358aed7070b8a152ead
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790637"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="2e498-102">Метод ICorPublishEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="2e498-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="2e498-103">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="2e498-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e498-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e498-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e498-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e498-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="2e498-106">заполняет Указатель на число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="2e498-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e498-107">Требования</span><span class="sxs-lookup"><span data-stu-id="2e498-107">Requirements</span></span>  
 <span data-ttu-id="2e498-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e498-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e498-109">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="2e498-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2e498-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e498-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e498-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e498-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e498-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e498-112">See also</span></span>

- [<span data-ttu-id="2e498-113">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="2e498-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
