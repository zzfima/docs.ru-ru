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
ms.openlocfilehash: add7239feb1cf6dab0fabe12e178336921211190
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414210"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="3d63d-102">Метод ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="3d63d-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="3d63d-103">Получает процесс, содержащий данный модуль.</span><span class="sxs-lookup"><span data-stu-id="3d63d-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d63d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d63d-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d63d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d63d-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="3d63d-106">[out] Указатель на адрес объекта ICorDebugProcess, который представляет процесс, содержащий данный модуль.</span><span class="sxs-lookup"><span data-stu-id="3d63d-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d63d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3d63d-107">Requirements</span></span>  
 <span data-ttu-id="3d63d-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d63d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d63d-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d63d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d63d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d63d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d63d-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d63d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
