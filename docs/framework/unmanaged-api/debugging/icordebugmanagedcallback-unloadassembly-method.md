---
title: Метод ICorDebugManagedCallback::UnloadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: 06c08499298656c8314d72667d9dac88c8d11e6a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788341"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="19dfa-102">Метод ICorDebugManagedCallback::UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="19dfa-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="19dfa-103">Уведомляет отладчик о том, что сборка среды CLR была выгружена.</span><span class="sxs-lookup"><span data-stu-id="19dfa-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19dfa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19dfa-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19dfa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="19dfa-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="19dfa-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий сборку.</span><span class="sxs-lookup"><span data-stu-id="19dfa-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="19dfa-107">окне Указатель на объект ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="19dfa-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19dfa-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="19dfa-108">Remarks</span></span>  
 <span data-ttu-id="19dfa-109">Сборка не должна использоваться после этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="19dfa-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19dfa-110">Требования</span><span class="sxs-lookup"><span data-stu-id="19dfa-110">Requirements</span></span>  
 <span data-ttu-id="19dfa-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19dfa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19dfa-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19dfa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19dfa-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19dfa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19dfa-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19dfa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19dfa-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="19dfa-115">See also</span></span>

- [<span data-ttu-id="19dfa-116">Метод LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="19dfa-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="19dfa-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="19dfa-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
