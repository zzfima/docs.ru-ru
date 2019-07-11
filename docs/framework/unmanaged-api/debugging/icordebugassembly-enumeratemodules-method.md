---
title: Методы ICorDebugAssembly::EnumerateModules
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.EnumerateModules
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1d8d76084bcf0b5951c6431c6f21f352406050b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737370"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="4b8c3-102">Методы ICorDebugAssembly::EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="4b8c3-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="4b8c3-103">Возвращает перечислитель для модулей, содержащихся в `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b8c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b8c3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b8c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b8c3-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="4b8c3-106">[out] Указатель на адрес интерфейс ICorDebugModuleEnum, который является перечислителем.</span><span class="sxs-lookup"><span data-stu-id="4b8c3-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b8c3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4b8c3-107">Requirements</span></span>  
 <span data-ttu-id="4b8c3-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b8c3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b8c3-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b8c3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b8c3-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b8c3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b8c3-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b8c3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
