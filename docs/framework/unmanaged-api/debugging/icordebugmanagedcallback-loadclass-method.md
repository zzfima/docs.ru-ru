---
title: "Метод ICorDebugManagedCallback::LoadClass"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3518a20567cdac8ed6587aa3dc06408ae6bf7b06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="706f4-102">Метод ICorDebugManagedCallback::LoadClass</span><span class="sxs-lookup"><span data-stu-id="706f4-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="706f4-103">Уведомляет отладчик о том, что класс был загружен.</span><span class="sxs-lookup"><span data-stu-id="706f4-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="706f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="706f4-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="706f4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="706f4-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="706f4-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в которую был загружен класса.</span><span class="sxs-lookup"><span data-stu-id="706f4-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="706f4-107">[in] Указатель на объект ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="706f4-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="706f4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="706f4-108">Remarks</span></span>  
 <span data-ttu-id="706f4-109">Этот обратный вызов происходит только в том случае, если загрузка класса была включена для модуля, содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="706f4-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="706f4-110">Загрузка класса всегда включена для динамических модулей.</span><span class="sxs-lookup"><span data-stu-id="706f4-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="706f4-111">`LoadClass` Обратный вызов обеспечивает подходящее время для связки точек останова для вновь созданных классов в динамических модулях.</span><span class="sxs-lookup"><span data-stu-id="706f4-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="706f4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="706f4-112">Requirements</span></span>  
 <span data-ttu-id="706f4-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="706f4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="706f4-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="706f4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="706f4-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="706f4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="706f4-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="706f4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="706f4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="706f4-117">See Also</span></span>  
 [<span data-ttu-id="706f4-118">Метод UnloadClass</span><span class="sxs-lookup"><span data-stu-id="706f4-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [<span data-ttu-id="706f4-119">ICorDebugManagedCallback-интерфейс</span><span class="sxs-lookup"><span data-stu-id="706f4-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
