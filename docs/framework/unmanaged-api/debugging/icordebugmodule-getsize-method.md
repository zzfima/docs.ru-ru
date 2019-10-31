---
title: Метод ICorDebugModule::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 402a0e8808b51fd4c09b254114292d4c851b2760
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129511"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="03e56-102">Метод ICorDebugModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="03e56-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="03e56-103">Возвращает размер модуля (в байтах).</span><span class="sxs-lookup"><span data-stu-id="03e56-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03e56-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03e56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03e56-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="03e56-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="03e56-106">заполняет Размер модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="03e56-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="03e56-107">Если модуль был создан из генератора образов в машинном кодах (NGen. exe), размер модуля будет равен нулю.</span><span class="sxs-lookup"><span data-stu-id="03e56-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03e56-108">Требования</span><span class="sxs-lookup"><span data-stu-id="03e56-108">Requirements</span></span>  
 <span data-ttu-id="03e56-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03e56-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03e56-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03e56-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03e56-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03e56-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03e56-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03e56-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
