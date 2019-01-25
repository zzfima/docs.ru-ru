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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d0d2c4af79a7d5a7123c5fe0ba043c2dd6302f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525811"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="84d26-102">Метод ICorDebugComObjectValue::GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="84d26-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="84d26-103">Предоставляет перечислитель для типов интерфейсов, что текущий объект был приведен к или использовать в качестве.</span><span class="sxs-lookup"><span data-stu-id="84d26-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84d26-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84d26-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84d26-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="84d26-106">[in] Значение, указывающее, возвращает ли метод только [!INCLUDE[wrt](../../../../includes/wrt-md.md)] интерфейсы (`IInspectable` интерфейсы) или все интерфейсами COM в вызываемая оболочка времени выполнения (RCW) в кэше.</span><span class="sxs-lookup"><span data-stu-id="84d26-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="84d26-107">[out] Указатель на адрес ICorDebugTypeEnum перечислителя, который предоставляет доступ к объектам ICorDebugType, представляющие типы кэшированных интерфейс отфильтрованы согласно `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="84d26-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84d26-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="84d26-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84d26-109">Требования</span><span class="sxs-lookup"><span data-stu-id="84d26-109">Requirements</span></span>  
 <span data-ttu-id="84d26-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84d26-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d26-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84d26-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84d26-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84d26-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84d26-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d26-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d26-114">См. также</span><span class="sxs-lookup"><span data-stu-id="84d26-114">See also</span></span>
- [<span data-ttu-id="84d26-115">Интерфейс ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="84d26-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="84d26-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="84d26-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
