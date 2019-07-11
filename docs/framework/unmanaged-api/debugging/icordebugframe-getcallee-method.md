---
title: Метод ICorDebugFrame::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10a5247632f242a4b4e0d33cf7fa7233d1b1e13b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754199"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="6f81e-102">Метод ICorDebugFrame::GetCallee</span><span class="sxs-lookup"><span data-stu-id="6f81e-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="6f81e-103">Получает указатель на объект ICorDebugFrame в текущей цепи, вызван этот кадр.</span><span class="sxs-lookup"><span data-stu-id="6f81e-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f81e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f81e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f81e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f81e-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="6f81e-106">[out] Указатель на адрес `ICorDebugFrame` , представляющий вызываемый кадр.</span><span class="sxs-lookup"><span data-stu-id="6f81e-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="6f81e-107">Это значение равно null, если вызывающий кадр внутренний кадр в текущей цепи.</span><span class="sxs-lookup"><span data-stu-id="6f81e-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f81e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="6f81e-108">Requirements</span></span>  
 <span data-ttu-id="6f81e-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f81e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f81e-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f81e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f81e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f81e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f81e-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f81e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
