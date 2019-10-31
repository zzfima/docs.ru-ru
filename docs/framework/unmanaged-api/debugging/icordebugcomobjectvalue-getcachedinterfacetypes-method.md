---
title: Метод ICorDebugComObjectValue::GetCachedInterfaceTypes
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: 199f58456e64ccf7ef771d42d5c7d64b189cb670
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125502"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="e1208-102">Метод ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="e1208-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="e1208-103">Предоставляет перечислитель для типов интерфейса, которые текущий объект приводят к типу или используются в качестве.</span><span class="sxs-lookup"><span data-stu-id="e1208-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1208-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1208-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1208-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1208-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="e1208-106">окне Значение, указывающее, возвращает ли метод только среда выполнения Windows интерфейсы (интерфейсы`IInspectable`) или все COM-интерфейсы, кэшированные вызываемой оболочкой времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="e1208-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="e1208-107">заполняет Указатель на адрес перечислителя ICorDebugTypeEnum, который предоставляет доступ к объектам ICorDebugType, представляющим кэшированные типы интерфейсов, отфильтрованные в соответствии с `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="e1208-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1208-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e1208-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1208-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e1208-109">Requirements</span></span>  
 <span data-ttu-id="e1208-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1208-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1208-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1208-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1208-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1208-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1208-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1208-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1208-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e1208-114">See also</span></span>

- [<span data-ttu-id="e1208-115">Интерфейс ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="e1208-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="e1208-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e1208-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
