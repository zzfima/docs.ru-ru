---
title: Метод ICorDebugThread::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
ms.openlocfilehash: 9793424e79ed878b04a5c51daad08b5d12d439e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791471"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="b0fc4-102">Метод ICorDebugThread::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="b0fc4-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="b0fc4-103">Возвращает указатель интерфейса на набор регистров, связанный с активной частью этого объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="b0fc4-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0fc4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0fc4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0fc4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0fc4-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="b0fc4-106">заполняет Указатель на адрес объекта интерфейса [ICorDebugRegisterSet](icordebugregisterset-interface.md) , представляющий набор регистров для активной части этого потока.</span><span class="sxs-lookup"><span data-stu-id="b0fc4-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0fc4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b0fc4-107">Requirements</span></span>  
 <span data-ttu-id="b0fc4-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0fc4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0fc4-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0fc4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0fc4-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0fc4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0fc4-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0fc4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
