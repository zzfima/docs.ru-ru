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
ms.openlocfilehash: 49b234b065eb66dc2ec0bc7e991117c5b54a92f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196353"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="999d6-102">Метод ICorDebugAssembly::GetProcess</span><span class="sxs-lookup"><span data-stu-id="999d6-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="999d6-103">Возвращает указатель интерфейса на процесс, в котором выполняется данный экземпляр ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="999d6-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="999d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="999d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="999d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="999d6-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="999d6-106">заполняет Указатель на интерфейс ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="999d6-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="999d6-107">Требования</span><span class="sxs-lookup"><span data-stu-id="999d6-107">Requirements</span></span>  
 <span data-ttu-id="999d6-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="999d6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="999d6-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="999d6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="999d6-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="999d6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="999d6-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="999d6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
