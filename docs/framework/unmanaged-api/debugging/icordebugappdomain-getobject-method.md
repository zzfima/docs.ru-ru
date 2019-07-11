---
title: Метод ICorDebugAppDomain::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737855"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="5ed33-102">Метод ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="5ed33-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="5ed33-103">Получает указатель интерфейса на домен приложения среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="5ed33-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ed33-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ed33-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ed33-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ed33-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="5ed33-106">[out] Указатель на адрес объекта интерфейса ICorDebugValue, который представляет домен приложения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5ed33-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ed33-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5ed33-107">Return Value</span></span>  
 <span data-ttu-id="5ed33-108">Если управляемый <xref:System.AppDomain?displayProperty=nameWithType> объект еще не был создан для этого домена приложения, метод возвращает `S_FALSE` и помещает `NULL` в `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="5ed33-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ed33-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ed33-109">Remarks</span></span>  
 <span data-ttu-id="5ed33-110">Каждый домен приложения в процессе может иметь управляемый <xref:System.AppDomain?displayProperty=nameWithType> объекта в среде выполнения, который ее представляет.</span><span class="sxs-lookup"><span data-stu-id="5ed33-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="5ed33-111">Эта функция возвращает объект интерфейс ICorDebugValue, соответствующий этому управляемых <xref:System.AppDomain?displayProperty=nameWithType> объекта.</span><span class="sxs-lookup"><span data-stu-id="5ed33-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ed33-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5ed33-112">Requirements</span></span>  
 <span data-ttu-id="5ed33-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ed33-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ed33-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ed33-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ed33-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ed33-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ed33-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ed33-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
