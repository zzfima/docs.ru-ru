---
title: "Метод ICorDebugFunction::GetNativeCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 15383198da740f536061f1568fb06f042117b19c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="449bb-102">Метод ICorDebugFunction::GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="449bb-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="449bb-103">Получает машинный код, представленный этим экземпляром ICorDebugFunction для функции.</span><span class="sxs-lookup"><span data-stu-id="449bb-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="449bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="449bb-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="449bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="449bb-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="449bb-106">[out] Указатель на интерфейс ICorDebugCode экземпляр, который представляет машинный код для этой функции или значение null, если эта функция представляет код MSIL (MSIL), еще не just-in-time (JIT) компиляции.</span><span class="sxs-lookup"><span data-stu-id="449bb-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="449bb-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="449bb-107">Remarks</span></span>  
 <span data-ttu-id="449bb-108">Если функция, представленный этим `ICorDebugFunction` экземпляр был JIT-компиляции более одного раза в случае универсальных типов, `GetNativeCode` возвращает объект случайных машинного кода.</span><span class="sxs-lookup"><span data-stu-id="449bb-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="449bb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="449bb-109">Requirements</span></span>  
 <span data-ttu-id="449bb-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="449bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="449bb-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="449bb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="449bb-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="449bb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="449bb-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="449bb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
