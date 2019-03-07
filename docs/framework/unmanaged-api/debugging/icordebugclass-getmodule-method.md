---
title: Метод ICorDebugClass::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e96d0d82b08449b4675ec7fd1517317006011ae
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478340"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="94773-102">Метод ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="94773-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="94773-103">Возвращает модуль, в котором определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="94773-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94773-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94773-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94773-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94773-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="94773-106">[out] Указатель на адрес ICorDebugModule объект, представляющий модуль, в котором определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="94773-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94773-107">Требования</span><span class="sxs-lookup"><span data-stu-id="94773-107">Requirements</span></span>  
 <span data-ttu-id="94773-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94773-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94773-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94773-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94773-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94773-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94773-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94773-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
