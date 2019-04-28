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
ms.openlocfilehash: c1af0f8f792c856c0b27b4d3d9ff557bcc5fce82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994868"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="982ae-102">Метод ICorDebugModule::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="982ae-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="982ae-103">Возвращает функцию, которое определяется токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="982ae-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="982ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="982ae-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="982ae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="982ae-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="982ae-106">[in] Объект `mdMethodDef` токен метаданных, который ссылается на метаданные функции.</span><span class="sxs-lookup"><span data-stu-id="982ae-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="982ae-107">[out] Указатель на адрес объекта интерфейса ICorDebugFunction, представляющий функцию.</span><span class="sxs-lookup"><span data-stu-id="982ae-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="982ae-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="982ae-108">Remarks</span></span>  
 <span data-ttu-id="982ae-109">`GetFunctionFromToken` Метод возвращает CORDBG_E_FUNCTION_NOT_IL HRESULT, если значение, переданное в `methodDef` не ссылается на метод Microsoft промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="982ae-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="982ae-110">Требования</span><span class="sxs-lookup"><span data-stu-id="982ae-110">Requirements</span></span>  
 <span data-ttu-id="982ae-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="982ae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="982ae-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="982ae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="982ae-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="982ae-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="982ae-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="982ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
