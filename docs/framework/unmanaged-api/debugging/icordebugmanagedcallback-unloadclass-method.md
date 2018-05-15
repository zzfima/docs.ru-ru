---
title: Метод ICorDebugManagedCallback::UnloadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e70a1c66baff2d91554dea47e248a7003e30c498
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="d99d9-102">Метод ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="d99d9-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="d99d9-103">Уведомляет отладчик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="d99d9-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d99d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d99d9-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d99d9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d99d9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d99d9-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий класс.</span><span class="sxs-lookup"><span data-stu-id="d99d9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="d99d9-107">[in] Указатель на объект ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="d99d9-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d99d9-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d99d9-108">Remarks</span></span>  
 <span data-ttu-id="d99d9-109">После этого вызова не должны ссылаться класса.</span><span class="sxs-lookup"><span data-stu-id="d99d9-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d99d9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d99d9-110">Requirements</span></span>  
 <span data-ttu-id="d99d9-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d99d9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d99d9-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d99d9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d99d9-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d99d9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d99d9-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d99d9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99d9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d99d9-115">See Also</span></span>  
 [<span data-ttu-id="d99d9-116">Метод LoadClass</span><span class="sxs-lookup"><span data-stu-id="d99d9-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)  
 [<span data-ttu-id="d99d9-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d99d9-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
