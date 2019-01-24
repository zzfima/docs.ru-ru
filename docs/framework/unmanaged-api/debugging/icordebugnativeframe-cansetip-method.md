---
title: Метод ICorDebugNativeFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 204cfc110ec6c8a11ec37505f8cf0c70d619e4b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660818"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="cc8b2-102">Метод ICorDebugNativeFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="cc8b2-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="cc8b2-103">Возвращает значение HRESULT, указывающее, является ли он безопасным задать указатель инструкций (IP) в указанное расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="cc8b2-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc8b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc8b2-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc8b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc8b2-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="cc8b2-106">[in] Нужное значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="cc8b2-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc8b2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc8b2-107">Remarks</span></span>  
 <span data-ttu-id="cc8b2-108">Используйте `CanSetIP` метод до вызова метода [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="cc8b2-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="cc8b2-109">Если `CanSetIP` возвращает любой HRESULT, отличных от S_OK, можно по-прежнему вызывать `ICorDebugNativeFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="cc8b2-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc8b2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cc8b2-110">Requirements</span></span>  
 <span data-ttu-id="cc8b2-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc8b2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc8b2-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc8b2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc8b2-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc8b2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc8b2-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc8b2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc8b2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cc8b2-115">See also</span></span>

