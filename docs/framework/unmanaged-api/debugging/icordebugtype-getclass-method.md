---
title: "Метод ICorDebugType::GetClass"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32462159bc00ea766af3e3bc0f9d3d7a35eb2e38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="ae28c-102">Метод ICorDebugType::GetClass</span><span class="sxs-lookup"><span data-stu-id="ae28c-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="ae28c-103">Получает указатель на интерфейс ICorDebugClass, который представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="ae28c-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae28c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae28c-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae28c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae28c-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="ae28c-106">[out] Указатель на адрес `ICorDebugClass` интерфейс, который представляет универсальный тип, у которого отсутствуют экземпляры.</span><span class="sxs-lookup"><span data-stu-id="ae28c-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae28c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ae28c-107">Remarks</span></span>  
 <span data-ttu-id="ae28c-108">`GetClass`может вызываться только при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="ae28c-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="ae28c-109">Вызовите [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) перед вызовом `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="ae28c-109">Call [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="ae28c-110">Если `ICorDebugType::GetType` возвращает значение CorElementType, ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, `GetClass` может быть вызван для получения типа без экземпляров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="ae28c-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae28c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ae28c-111">Requirements</span></span>  
 <span data-ttu-id="ae28c-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae28c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae28c-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae28c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae28c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae28c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae28c-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae28c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
