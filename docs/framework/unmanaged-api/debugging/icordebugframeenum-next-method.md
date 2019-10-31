---
title: Метод ICorDebugFrameEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: ff74a9849b74b8a8e6b8c03f1fc4e7c7eee1ec14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124059"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="7fbd8-102">Метод ICorDebugFrameEnum::Next</span><span class="sxs-lookup"><span data-stu-id="7fbd8-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="7fbd8-103">Возвращает указанное число экземпляров ICorDebugFrame, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="7fbd8-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fbd8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7fbd8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fbd8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7fbd8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7fbd8-106">окне Число извлекаемых экземпляров `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="7fbd8-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="7fbd8-107">заполняет Массив указателей, каждый из которых указывает на объект `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="7fbd8-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7fbd8-108">заполняет Указатель на число фактически возвращаемых экземпляров `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="7fbd8-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="7fbd8-109">Это значение может быть равно null, если `celt` является одним.</span><span class="sxs-lookup"><span data-stu-id="7fbd8-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fbd8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7fbd8-110">Requirements</span></span>  
 <span data-ttu-id="7fbd8-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fbd8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fbd8-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fbd8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fbd8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fbd8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fbd8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fbd8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
