---
title: Метод ICorDebugFunction::GetNativeCode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb85c4b2c26c136a5f9fc05221a42c4bc99f37f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470176"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="e6076-102">Метод ICorDebugFunction::GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="e6076-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="e6076-103">Получает машинный код для функции, представленного данным экземпляром ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="e6076-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6076-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6076-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6076-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6076-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="e6076-106">[out] Указатель на интерфейс ICorDebugCode экземпляр, который представляет машинный код для этой функции, или значение null, если эта функция представляет код MSIL (MSIL), не был just-in-time (JIT) компиляции.</span><span class="sxs-lookup"><span data-stu-id="e6076-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6076-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6076-107">Remarks</span></span>  
 <span data-ttu-id="e6076-108">Если функция, которая представляется этим `ICorDebugFunction` экземпляр был JIT-компиляции более одного раза, как в случае универсальных типов `GetNativeCode` возвращает объект случайных машинного кода.</span><span class="sxs-lookup"><span data-stu-id="e6076-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6076-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e6076-109">Requirements</span></span>  
 <span data-ttu-id="e6076-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6076-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6076-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6076-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6076-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6076-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6076-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6076-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
