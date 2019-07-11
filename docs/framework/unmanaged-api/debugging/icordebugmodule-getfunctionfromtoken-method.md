---
title: Метод ICorDebugModule::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 547986633172d6f5e6549ad2048833dc9fb0cef3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763465"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="9ae93-102">Метод ICorDebugModule::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="9ae93-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="9ae93-103">Возвращает функцию, которое определяется токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="9ae93-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ae93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ae93-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ae93-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="9ae93-106">[in] Объект `mdMethodDef` токен метаданных, который ссылается на метаданные функции.</span><span class="sxs-lookup"><span data-stu-id="9ae93-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="9ae93-107">[out] Указатель на адрес объекта интерфейса ICorDebugFunction, представляющий функцию.</span><span class="sxs-lookup"><span data-stu-id="9ae93-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ae93-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ae93-108">Remarks</span></span>  
 <span data-ttu-id="9ae93-109">`GetFunctionFromToken` Метод возвращает CORDBG_E_FUNCTION_NOT_IL HRESULT, если значение, переданное в `methodDef` не ссылается на метод Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="9ae93-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ae93-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9ae93-110">Requirements</span></span>  
 <span data-ttu-id="9ae93-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ae93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae93-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ae93-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ae93-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ae93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ae93-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
