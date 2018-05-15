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
ms.openlocfilehash: d62f4f8a34123bcd3f0cbe56f1c1b958bcaa6ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="1afa0-102">Метод ICorDebugFrame::GetCallee</span><span class="sxs-lookup"><span data-stu-id="1afa0-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="1afa0-103">Возвращает указатель на объект ICorDebugFrame в текущей цепи, вызванной этим кадром.</span><span class="sxs-lookup"><span data-stu-id="1afa0-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1afa0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1afa0-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1afa0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1afa0-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="1afa0-106">[out] Указатель на адрес `ICorDebugFrame` , представляющий вызываемый кадр.</span><span class="sxs-lookup"><span data-stu-id="1afa0-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="1afa0-107">Это значение равно null, если вызывающий кадр является самым внутренним кадром в текущей цепи.</span><span class="sxs-lookup"><span data-stu-id="1afa0-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1afa0-108">Требования</span><span class="sxs-lookup"><span data-stu-id="1afa0-108">Requirements</span></span>  
 <span data-ttu-id="1afa0-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1afa0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1afa0-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1afa0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1afa0-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1afa0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1afa0-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1afa0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
