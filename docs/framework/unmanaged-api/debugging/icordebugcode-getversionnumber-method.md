---
title: Метод ICorDebugCode::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type:
- apiref
ms.openlocfilehash: 646c20ca1b78ff0ce513b8a3c9b578c3b1b9a696
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125601"
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="367b9-102">Метод ICorDebugCode::GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="367b9-102">ICorDebugCode::GetVersionNumber Method</span></span>

<span data-ttu-id="367b9-103">Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет этот "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="367b9-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>

## <a name="syntax"></a><span data-ttu-id="367b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="367b9-104">Syntax</span></span>

```cpp
HRESULT GetVersionNumber (
    [out] ULONG32    *nVersion
);
```

## <a name="parameters"></a><span data-ttu-id="367b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="367b9-105">Parameters</span></span>

 `nVersion`  
 <span data-ttu-id="367b9-106">заполняет Указатель на номер версии кода.</span><span class="sxs-lookup"><span data-stu-id="367b9-106">[out] A pointer to the version number of the code.</span></span>

## <a name="remarks"></a><span data-ttu-id="367b9-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="367b9-107">Remarks</span></span>

 <span data-ttu-id="367b9-108">Номер версии увеличивается каждый раз, когда в коде выполняется операция "изменить и продолжить" (EnC).</span><span class="sxs-lookup"><span data-stu-id="367b9-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>

## <a name="requirements"></a><span data-ttu-id="367b9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="367b9-109">Requirements</span></span>

 <span data-ttu-id="367b9-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="367b9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="367b9-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="367b9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="367b9-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="367b9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="367b9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="367b9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
