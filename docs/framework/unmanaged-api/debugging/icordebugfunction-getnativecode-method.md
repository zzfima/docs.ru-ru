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
ms.openlocfilehash: 5bb41b2b49922475550997f18832b391522e2f26
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137873"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="97782-102">Метод ICorDebugFunction::GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="97782-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="97782-103">Возвращает машинный код для функции, представленной этим экземпляром ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="97782-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97782-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97782-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97782-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="97782-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="97782-106">заполняет Указатель на экземпляр ICorDebugCode, представляющий машинный код для этой функции, или значение null, если эта функция является кодом MSIL, который не был скомпилирован JIT-КОМПИЛЯТОРом.</span><span class="sxs-lookup"><span data-stu-id="97782-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97782-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="97782-107">Remarks</span></span>  
 <span data-ttu-id="97782-108">Если функция, представленная этим `ICorDebugFunction`ным экземпляром, была скомпилирована JIT-компилятором более одного раза, как в случае универсальных типов, `GetNativeCode` Возвращает произвольный объект машинного кода.</span><span class="sxs-lookup"><span data-stu-id="97782-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97782-109">Требования</span><span class="sxs-lookup"><span data-stu-id="97782-109">Requirements</span></span>  
 <span data-ttu-id="97782-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97782-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97782-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97782-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97782-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97782-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97782-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97782-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
