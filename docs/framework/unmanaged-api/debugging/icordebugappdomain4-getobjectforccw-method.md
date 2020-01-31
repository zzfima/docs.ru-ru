---
title: Метод ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
ms.openlocfilehash: 50f46394c809321f0bd256e4c8d75b76fc7c2c70
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784851"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a><span data-ttu-id="fc142-102">Метод ICorDebugAppDomain4::GetObjectForCCW</span><span class="sxs-lookup"><span data-stu-id="fc142-102">ICorDebugAppDomain4::GetObjectForCCW Method</span></span>
<span data-ttu-id="fc142-103">Возвращает управляемый объект из вызываемой оболочки COMr (CCW).</span><span class="sxs-lookup"><span data-stu-id="fc142-103">Gets a managed object from a COM callable wrapper (CCW) pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc142-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc142-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc142-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc142-105">Parameters</span></span>  
 `ccwPointer`  
 <span data-ttu-id="fc142-106">[in] Указатель вызываемой оболочки COM (CCW).</span><span class="sxs-lookup"><span data-stu-id="fc142-106">[in] A COM callable wrapper (CCW) pointer.</span></span>  
  
 `ppManagedObject`  
 <span data-ttu-id="fc142-107">заполняет Указатель на адрес объекта ICorDebugValue, который представляет управляемый объект, соответствующий заданному указателю CCW.</span><span class="sxs-lookup"><span data-stu-id="fc142-107">[out] A pointer to the address of an "ICorDebugValue" object that represents the managed object that corresponds to the given CCW pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc142-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="fc142-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc142-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fc142-109">Requirements</span></span>  
 <span data-ttu-id="fc142-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc142-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc142-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc142-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc142-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc142-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc142-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc142-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc142-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc142-114">See also</span></span>

- [<span data-ttu-id="fc142-115">Интерфейс ICorDebugAppDomain4</span><span class="sxs-lookup"><span data-stu-id="fc142-115">ICorDebugAppDomain4 Interface</span></span>](icordebugappdomain4-interface.md)
- [<span data-ttu-id="fc142-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fc142-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
