---
title: Метод ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: a862dd3f6a9c10c6b3a5a0bb41208d351c4ca9f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125690"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="bda40-102">Метод ICorDebugClass2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="bda40-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="bda40-103">Для каждого метода класса задает значение, указывающее, является ли метод определяемым пользователем кодом.</span><span class="sxs-lookup"><span data-stu-id="bda40-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bda40-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bda40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bda40-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="bda40-106">окне Задайте значение `true`, чтобы указать, что метод является определяемым пользователем кодом; в противном случае задайте значение `false`.</span><span class="sxs-lookup"><span data-stu-id="bda40-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bda40-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="bda40-107">Remarks</span></span>  
 <span data-ttu-id="bda40-108">Средство "только мой код" (JMC) пропускает код, не определенный пользователем.</span><span class="sxs-lookup"><span data-stu-id="bda40-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="bda40-109">Определяемый пользователем код должен быть подмножеством отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="bda40-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="bda40-110">`SetJMCStatus` возвращает значение HRESULT, равное S_FALSE, если не удается задать значение для какого бы то ни было метода, даже если оно успешно задает значение для всех других методов.</span><span class="sxs-lookup"><span data-stu-id="bda40-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda40-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bda40-111">Requirements</span></span>  
 <span data-ttu-id="bda40-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda40-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda40-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bda40-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bda40-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bda40-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bda40-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda40-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
