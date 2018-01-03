---
title: "Метод ICorDebugAppDomain::GetObject"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetObject
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f8206c6e5efbee8522f425f9078d99a39bbdd42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="ae2d0-102">Метод ICorDebugAppDomain::GetObject</span><span class="sxs-lookup"><span data-stu-id="ae2d0-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="ae2d0-103">Получает указатель интерфейса на домен приложения среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="ae2d0-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae2d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae2d0-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae2d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae2d0-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="ae2d0-106">[out] Указатель на адрес объекта интерфейса ICorDebugValue, представляющий домен приложения со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="ae2d0-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae2d0-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ae2d0-107">Return Value</span></span>  
 <span data-ttu-id="ae2d0-108">Если управляемый <xref:System.AppDomain?displayProperty=nameWithType> объект еще не был создан для этого домена приложения, метод возвращает `S_FALSE` и помещает `NULL` в `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="ae2d0-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae2d0-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ae2d0-109">Remarks</span></span>  
 <span data-ttu-id="ae2d0-110">Каждый домен приложения в процессе, возможно, управляемый <xref:System.AppDomain?displayProperty=nameWithType> объекта в среде выполнения, который ее представляет.</span><span class="sxs-lookup"><span data-stu-id="ae2d0-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="ae2d0-111">Эта функция возвращает объект ICorDebugValue-интерфейс, соответствующий управляемый <xref:System.AppDomain?displayProperty=nameWithType> объекта.</span><span class="sxs-lookup"><span data-stu-id="ae2d0-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae2d0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ae2d0-112">Requirements</span></span>  
 <span data-ttu-id="ae2d0-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae2d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae2d0-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae2d0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae2d0-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae2d0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae2d0-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae2d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
