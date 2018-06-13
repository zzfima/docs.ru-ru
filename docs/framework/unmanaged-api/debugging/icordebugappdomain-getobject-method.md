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
ms.openlocfilehash: a6f528bcef7d06b503b1ee9d7bd4a61d3d3e9672
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406524"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="9b948-102">Метод ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="9b948-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="9b948-103">Получает указатель интерфейса на домен приложения среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="9b948-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b948-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b948-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b948-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b948-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="9b948-106">[out] Указатель на адрес объекта интерфейса ICorDebugValue, представляющий домен приложения со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="9b948-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b948-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9b948-107">Return Value</span></span>  
 <span data-ttu-id="9b948-108">Если управляемый <xref:System.AppDomain?displayProperty=nameWithType> объект еще не был создан для этого домена приложения, метод возвращает `S_FALSE` и помещает `NULL` в `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="9b948-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b948-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b948-109">Remarks</span></span>  
 <span data-ttu-id="9b948-110">Каждый домен приложения в процессе, возможно, управляемый <xref:System.AppDomain?displayProperty=nameWithType> объекта в среде выполнения, который ее представляет.</span><span class="sxs-lookup"><span data-stu-id="9b948-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="9b948-111">Эта функция возвращает объект ICorDebugValue-интерфейс, соответствующий управляемый <xref:System.AppDomain?displayProperty=nameWithType> объекта.</span><span class="sxs-lookup"><span data-stu-id="9b948-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b948-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9b948-112">Requirements</span></span>  
 <span data-ttu-id="9b948-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b948-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b948-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b948-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b948-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b948-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b948-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b948-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
