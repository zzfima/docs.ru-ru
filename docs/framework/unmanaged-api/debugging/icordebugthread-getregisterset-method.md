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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc218370779742055e14dc62a8475c42c344c40c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418738"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="e5f81-102">Метод ICorDebugThread::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="e5f81-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="e5f81-103">Получает указатель интерфейса на набор регистров, которая связана с активной части данного объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="e5f81-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5f81-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5f81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5f81-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="e5f81-106">[out] Указатель на адрес [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) объект интерфейса, представляющий регистра задать для активной части данного потока.</span><span class="sxs-lookup"><span data-stu-id="e5f81-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f81-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e5f81-107">Requirements</span></span>  
 <span data-ttu-id="e5f81-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5f81-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f81-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5f81-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5f81-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5f81-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5f81-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f81-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
