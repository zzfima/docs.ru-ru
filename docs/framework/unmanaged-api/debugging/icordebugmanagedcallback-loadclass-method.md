---
title: "Метод ICorDebugManagedCallback::LoadClass"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f3e732b418398e9c917085d22507c9304981b06a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="8c8fc-102">Метод ICorDebugManagedCallback::LoadClass</span><span class="sxs-lookup"><span data-stu-id="8c8fc-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="8c8fc-103">Уведомляет отладчик о том, что класс был загружен.</span><span class="sxs-lookup"><span data-stu-id="8c8fc-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c8fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c8fc-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c8fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c8fc-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8c8fc-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в которую был загружен класса.</span><span class="sxs-lookup"><span data-stu-id="8c8fc-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="8c8fc-107">[in] Указатель на объект ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="8c8fc-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c8fc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c8fc-108">Remarks</span></span>  
 <span data-ttu-id="8c8fc-109">Этот обратный вызов происходит только в том случае, если загрузка класса была включена для модуля, содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="8c8fc-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="8c8fc-110">Загрузка класса всегда включена для динамических модулей.</span><span class="sxs-lookup"><span data-stu-id="8c8fc-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="8c8fc-111">`LoadClass` Обратный вызов обеспечивает подходящее время для связки точек останова для вновь созданных классов в динамических модулях.</span><span class="sxs-lookup"><span data-stu-id="8c8fc-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c8fc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8c8fc-112">Requirements</span></span>  
 <span data-ttu-id="8c8fc-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c8fc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c8fc-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c8fc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c8fc-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c8fc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c8fc-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c8fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8fc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8c8fc-117">See Also</span></span>  
 [<span data-ttu-id="8c8fc-118">Метод UnloadClass</span><span class="sxs-lookup"><span data-stu-id="8c8fc-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [<span data-ttu-id="8c8fc-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="8c8fc-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
