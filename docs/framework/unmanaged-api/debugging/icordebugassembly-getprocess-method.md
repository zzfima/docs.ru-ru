---
title: Метод ICorDebugAssembly::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0d5b6648fe6ce8a42f343d3cbdd77eb026b8f13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744476"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="559ba-102">Метод ICorDebugAssembly::GetProcess</span><span class="sxs-lookup"><span data-stu-id="559ba-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="559ba-103">Получает указатель интерфейса на процесс, в котором выполняется этот экземпляр ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="559ba-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="559ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="559ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="559ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="559ba-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="559ba-106">[out] Указатель на интерфейс ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="559ba-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="559ba-107">Требования</span><span class="sxs-lookup"><span data-stu-id="559ba-107">Requirements</span></span>  
 <span data-ttu-id="559ba-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="559ba-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="559ba-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="559ba-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="559ba-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="559ba-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="559ba-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="559ba-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
