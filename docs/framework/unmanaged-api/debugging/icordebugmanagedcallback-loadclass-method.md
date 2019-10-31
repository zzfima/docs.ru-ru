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
ms.openlocfilehash: d23b695550c8444264934f7aca4fa185064e89c5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130730"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="5a073-102">Метод ICorDebugManagedCallback::LoadClass</span><span class="sxs-lookup"><span data-stu-id="5a073-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="5a073-103">Уведомляет отладчик о том, что класс был загружен.</span><span class="sxs-lookup"><span data-stu-id="5a073-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a073-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a073-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a073-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a073-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5a073-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в который был загружен класс.</span><span class="sxs-lookup"><span data-stu-id="5a073-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="5a073-107">окне Указатель на объект ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="5a073-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a073-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="5a073-108">Remarks</span></span>  
 <span data-ttu-id="5a073-109">Этот обратный вызов происходит, только если для модуля, содержащего класс, была включена загрузка класса.</span><span class="sxs-lookup"><span data-stu-id="5a073-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="5a073-110">Загрузка класса всегда включена для динамических модулей.</span><span class="sxs-lookup"><span data-stu-id="5a073-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="5a073-111">Обратный вызов `LoadClass` предоставляет соответствующее время для привязки точек останова к вновь созданным классам в динамических модулях.</span><span class="sxs-lookup"><span data-stu-id="5a073-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a073-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5a073-112">Requirements</span></span>  
 <span data-ttu-id="5a073-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a073-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a073-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a073-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a073-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a073-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a073-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a073-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a073-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5a073-117">See also</span></span>

- [<span data-ttu-id="5a073-118">Метод UnloadClass</span><span class="sxs-lookup"><span data-stu-id="5a073-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="5a073-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5a073-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
