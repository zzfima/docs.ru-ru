---
title: Метод ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0915027ce6a3768ff854eafc5496c5057081cc4d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499541"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="52e88-102">Метод ICorDebugType::GetClass</span><span class="sxs-lookup"><span data-stu-id="52e88-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="52e88-103">Получает указатель на интерфейс ICorDebugClass, представляющий универсального типа без экземпляров.</span><span class="sxs-lookup"><span data-stu-id="52e88-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52e88-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52e88-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52e88-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="52e88-106">[out] Указатель на адрес `ICorDebugClass` интерфейс, который представляет универсального типа без экземпляров.</span><span class="sxs-lookup"><span data-stu-id="52e88-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52e88-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="52e88-107">Remarks</span></span>  
 <span data-ttu-id="52e88-108">`GetClass` может вызываться только при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="52e88-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="52e88-109">Вызовите [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) перед вызовом `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="52e88-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="52e88-110">Если `ICorDebugType::GetType` возвращает значение CorElementType ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, `GetClass` может вызываться для получения типа без экземпляров для универсального типа.</span><span class="sxs-lookup"><span data-stu-id="52e88-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52e88-111">Требования</span><span class="sxs-lookup"><span data-stu-id="52e88-111">Requirements</span></span>  
 <span data-ttu-id="52e88-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52e88-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52e88-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52e88-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52e88-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52e88-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52e88-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52e88-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
