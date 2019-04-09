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
ms.openlocfilehash: bd16db8c009fe81f2674a8bf9c7ad3a2a4827777
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092855"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="5c753-102">Метод ICorDebugNativeFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="5c753-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="5c753-103">Возвращает значение HRESULT, указывающее, является ли он безопасным задать указатель инструкций (IP) в указанное расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="5c753-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c753-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c753-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c753-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c753-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="5c753-106">[in] Нужное значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="5c753-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c753-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c753-107">Remarks</span></span>  
 <span data-ttu-id="5c753-108">Используйте `CanSetIP` метод до вызова метода [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="5c753-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="5c753-109">Если `CanSetIP` возвращает любой HRESULT, отличных от S_OK, можно по-прежнему вызывать `ICorDebugNativeFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="5c753-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c753-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5c753-110">Requirements</span></span>  
 <span data-ttu-id="5c753-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c753-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c753-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c753-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c753-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c753-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5c753-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5c753-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c753-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5c753-115">See also</span></span>
