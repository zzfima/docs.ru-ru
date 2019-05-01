---
title: Метод ICorDebugModule::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97cecd66462cf6a88012b13dec82dbf617891dd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988004"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="1699e-102">Метод ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="1699e-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="1699e-103">Получает процесс, содержащий данный модуль.</span><span class="sxs-lookup"><span data-stu-id="1699e-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1699e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1699e-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1699e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1699e-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="1699e-106">[out] Указатель на адрес ICorDebugProcess объект, представляющий процесс, содержащий данный модуль.</span><span class="sxs-lookup"><span data-stu-id="1699e-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1699e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1699e-107">Requirements</span></span>  
 <span data-ttu-id="1699e-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1699e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1699e-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1699e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1699e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1699e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1699e-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1699e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
