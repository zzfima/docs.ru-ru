---
title: Метод ICorDebugILFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49cef22e88613fe4c4dfb3fb35a92977977b1827
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988641"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="76f7c-102">Метод ICorDebugILFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="76f7c-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="76f7c-103">Возвращает значение HRESULT, указывающее, является ли он безопасным задать указатель инструкций в указанное расположение смещения в коде Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="76f7c-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76f7c-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="76f7c-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="76f7c-106">[in] Нужное значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="76f7c-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76f7c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="76f7c-107">Remarks</span></span>  
 <span data-ttu-id="76f7c-108">Используйте `CanSetIP` метод перед вызовом [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="76f7c-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="76f7c-109">Если `CanSetIP` возвращает любой HRESULT, отличных от S_OK, можно по-прежнему вызывать `ICorDebugILFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="76f7c-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76f7c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="76f7c-110">Requirements</span></span>  
 <span data-ttu-id="76f7c-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76f7c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f7c-112">**Заголовок.** H CorDebug.idl, CorDebug,</span><span class="sxs-lookup"><span data-stu-id="76f7c-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="76f7c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76f7c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76f7c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76f7c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
