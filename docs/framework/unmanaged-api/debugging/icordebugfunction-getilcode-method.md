---
title: Метод ICorDebugFunction::GetILCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: c2ce4b95de75bef3928e144656b565676568caa0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137900"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="fa5f0-102">Метод ICorDebugFunction::GetILCode</span><span class="sxs-lookup"><span data-stu-id="fa5f0-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="fa5f0-103">Возвращает экземпляр ICorDebugCode, представляющий код на языке MSIL, связанный с данным объектом ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="fa5f0-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa5f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa5f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa5f0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa5f0-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="fa5f0-106">заполняет Указатель на экземпляр `ICorDebugCode` или значение null, если функция не была скомпилирована в MSIL.</span><span class="sxs-lookup"><span data-stu-id="fa5f0-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa5f0-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="fa5f0-107">Remarks</span></span>  
 <span data-ttu-id="fa5f0-108">Если для этой функции разрешено изменение и продолжение, то метод `GetILCode` получит код MSIL, соответствующий измененной версии кода этой функции в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="fa5f0-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa5f0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fa5f0-109">Requirements</span></span>  
 <span data-ttu-id="fa5f0-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa5f0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa5f0-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa5f0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa5f0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa5f0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa5f0-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa5f0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
