---
title: Метод ICorDebugCode::IsIL
ms.date: 03/30/2017
api_name:
- ICorDebugCode.IsIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::IsIL
helpviewer_keywords:
- ICorDebugCode::IsIL method [.NET Framework debugging]
- IsIL method [.NET Framework debugging]
ms.assetid: 132ef8cc-d938-43f3-b8f2-e3b97c0ceb33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a81f4a53954c559ab12e27bcf039b7b1a1804cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700798"
---
# <a name="icordebugcodeisil-method"></a><span data-ttu-id="0b79b-102">Метод ICorDebugCode::IsIL</span><span class="sxs-lookup"><span data-stu-id="0b79b-102">ICorDebugCode::IsIL Method</span></span>

<span data-ttu-id="0b79b-103">Возвращает значение, указывающее, представляет ли этот "ICorDebugCode" код, скомпилированный на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="0b79b-103">Gets a value that indicates whether this "ICorDebugCode" represents code that was compiled in Microsoft intermediate language (MSIL).</span></span>

## <a name="syntax"></a><span data-ttu-id="0b79b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b79b-104">Syntax</span></span>

```cpp
HRESULT IsIL (
    [out] BOOL       *pbIL
);
```

## <a name="parameters"></a><span data-ttu-id="0b79b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b79b-105">Parameters</span></span>
 `pbIL`  
 <span data-ttu-id="0b79b-106">[out] `true`, если этот `ICorDebugCode` представляет код, скомпилированный в MSIL; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="0b79b-106">[out] `true` if this `ICorDebugCode` represents code that was compiled in MSIL; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b79b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="0b79b-107">Requirements</span></span>

 <span data-ttu-id="0b79b-108">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b79b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  

 <span data-ttu-id="0b79b-109">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0b79b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  

 <span data-ttu-id="0b79b-110">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="0b79b-110">**Library:** CorGuids.lib</span></span>  

 <span data-ttu-id="0b79b-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b79b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
 
