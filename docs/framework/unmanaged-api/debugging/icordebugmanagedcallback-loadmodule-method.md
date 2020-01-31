---
title: Метод ICorDebugManagedCallback::LoadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 21a97f140a41f8f380c1334652bc2417e19659c6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777140"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="8a175-102">Метод ICorDebugManagedCallback::LoadModule</span><span class="sxs-lookup"><span data-stu-id="8a175-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="8a175-103">Уведомляет отладчик о том, что модуль среды CLR успешно загружен.</span><span class="sxs-lookup"><span data-stu-id="8a175-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a175-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a175-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a175-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a175-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8a175-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в который был загружен модуль.</span><span class="sxs-lookup"><span data-stu-id="8a175-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="8a175-107">окне Указатель на объект ICorDebugModule, представляющий модуль CLR.</span><span class="sxs-lookup"><span data-stu-id="8a175-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a175-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="8a175-108">Remarks</span></span>  
 <span data-ttu-id="8a175-109">Обратный вызов `LoadModule` предоставляет подходящее время для проверки метаданных модуля, установки флагов JIT-компилятора или включения или отключения обратных вызовов при загрузке класса для модуля.</span><span class="sxs-lookup"><span data-stu-id="8a175-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a175-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8a175-110">Requirements</span></span>  
 <span data-ttu-id="8a175-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a175-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a175-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a175-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a175-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a175-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a175-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a175-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a175-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a175-115">See also</span></span>

- [<span data-ttu-id="8a175-116">Метод UnloadModule</span><span class="sxs-lookup"><span data-stu-id="8a175-116">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="8a175-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="8a175-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
