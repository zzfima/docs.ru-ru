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
ms.openlocfilehash: 354de38e106ea16eef10bd9a9cebf2b27ca44d25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548132"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="890c3-102">Метод ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="890c3-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="890c3-103">Уведомляет отладчик о выгрузке класса.</span><span class="sxs-lookup"><span data-stu-id="890c3-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="890c3-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="890c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="890c3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="890c3-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий класс.</span><span class="sxs-lookup"><span data-stu-id="890c3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="890c3-107">[in] Указатель на объект, представляющий класс ICorDebugClass.</span><span class="sxs-lookup"><span data-stu-id="890c3-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="890c3-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="890c3-108">Remarks</span></span>  
 <span data-ttu-id="890c3-109">Не следует ссылаться класса после этого вызова.</span><span class="sxs-lookup"><span data-stu-id="890c3-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="890c3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="890c3-110">Requirements</span></span>  
 <span data-ttu-id="890c3-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="890c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="890c3-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="890c3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="890c3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="890c3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="890c3-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="890c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890c3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="890c3-115">See also</span></span>
- [<span data-ttu-id="890c3-116">Метод LoadClass</span><span class="sxs-lookup"><span data-stu-id="890c3-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="890c3-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="890c3-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
