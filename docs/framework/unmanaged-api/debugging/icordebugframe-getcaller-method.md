---
title: Метод ICorDebugFrame::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82902e6a395fe62464065ccea4cca5b52c960f0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988823"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="efb13-102">Метод ICorDebugFrame::GetCaller</span><span class="sxs-lookup"><span data-stu-id="efb13-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="efb13-103">Получает указатель на объект ICorDebugFrame в текущей цепи, вызван этот кадр.</span><span class="sxs-lookup"><span data-stu-id="efb13-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efb13-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb13-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="efb13-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="efb13-106">[out] Указатель на адрес `ICorDebugFrame` , представляющий вызывающий кадр.</span><span class="sxs-lookup"><span data-stu-id="efb13-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="efb13-107">Это значение равно null, если вызываемый кадр является самым крайним кадром в текущей цепи.</span><span class="sxs-lookup"><span data-stu-id="efb13-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb13-108">Требования</span><span class="sxs-lookup"><span data-stu-id="efb13-108">Requirements</span></span>  
 <span data-ttu-id="efb13-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efb13-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb13-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efb13-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efb13-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efb13-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efb13-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb13-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
