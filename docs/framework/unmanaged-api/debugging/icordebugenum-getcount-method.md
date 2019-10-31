---
title: Метод ICorDebugEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
ms.openlocfilehash: 208d5d2e3ca571a1c23a9322c05e784bd2238d61
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124689"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="c7180-102">Метод ICorDebugEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="c7180-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="c7180-103">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="c7180-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7180-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7180-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7180-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7180-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="c7180-106">заполняет Указатель на число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="c7180-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7180-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c7180-107">Requirements</span></span>  
 <span data-ttu-id="c7180-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7180-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7180-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7180-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7180-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7180-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7180-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7180-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
