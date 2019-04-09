---
title: Метод ICorDebugManagedCallback::LoadClass
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39ce3e8329c4ff32b55341127f68a800246677df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169953"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="fc86a-102">Метод ICorDebugManagedCallback::LoadClass</span><span class="sxs-lookup"><span data-stu-id="fc86a-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="fc86a-103">Уведомляет отладчик о том, что класс был загружен.</span><span class="sxs-lookup"><span data-stu-id="fc86a-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc86a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc86a-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc86a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc86a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fc86a-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в которую был загружен класс.</span><span class="sxs-lookup"><span data-stu-id="fc86a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="fc86a-107">[in] Указатель на объект, представляющий класс ICorDebugClass.</span><span class="sxs-lookup"><span data-stu-id="fc86a-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc86a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="fc86a-108">Remarks</span></span>  
 <span data-ttu-id="fc86a-109">Этот обратный вызов происходит только в том случае, если загрузка класса была включена для модуля, содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="fc86a-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="fc86a-110">Загрузка класса всегда включена для динамических модулей.</span><span class="sxs-lookup"><span data-stu-id="fc86a-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="fc86a-111">`LoadClass` Обратного вызова предоставляет подходящий момент привязка точки останова к только что созданных классов в динамических модулях.</span><span class="sxs-lookup"><span data-stu-id="fc86a-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc86a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fc86a-112">Requirements</span></span>  
 <span data-ttu-id="fc86a-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc86a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc86a-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc86a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc86a-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc86a-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fc86a-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fc86a-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc86a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fc86a-117">See also</span></span>

- [<span data-ttu-id="fc86a-118">Метод UnloadClass</span><span class="sxs-lookup"><span data-stu-id="fc86a-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="fc86a-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fc86a-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
