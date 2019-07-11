---
title: Метод ICorDebugThread::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3695f150797e6a59a2fb1d58c99f233a35d687ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771844"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="93a5a-102">Метод ICorDebugThread::GetObject</span><span class="sxs-lookup"><span data-stu-id="93a5a-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="93a5a-103">Получает указатель интерфейса среды выполнения (CLR) потоку выполнения.</span><span class="sxs-lookup"><span data-stu-id="93a5a-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93a5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93a5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93a5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93a5a-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="93a5a-106">[out] Указатель на адрес объекта интерфейса ICorDebugValue, представляющий потока среды CLR.</span><span class="sxs-lookup"><span data-stu-id="93a5a-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93a5a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="93a5a-107">Requirements</span></span>  
 <span data-ttu-id="93a5a-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93a5a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93a5a-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93a5a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93a5a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93a5a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93a5a-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93a5a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a5a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="93a5a-112">See also</span></span>

- <xref:System.Threading.Thread>
