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
ms.openlocfilehash: 7fa90aff73d94baf2cbf7d01f41710cb2aa10213
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994010"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="3eb6d-102">Метод ICorDebugThread::GetObject</span><span class="sxs-lookup"><span data-stu-id="3eb6d-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="3eb6d-103">Получает указатель интерфейса среды выполнения (CLR) потоку выполнения.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eb6d-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eb6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3eb6d-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="3eb6d-106">[out] Указатель на адрес объекта интерфейса ICorDebugValue, представляющий потока среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3eb6d-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb6d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3eb6d-107">Requirements</span></span>  
 <span data-ttu-id="3eb6d-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eb6d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb6d-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3eb6d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3eb6d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eb6d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eb6d-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb6d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb6d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3eb6d-112">See also</span></span>

- <xref:System.Threading.Thread>
