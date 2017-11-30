---
title: "Метод ICorDebugNativeFrame::CanSetIP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.CanSetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33b5efe6352d3a0c30179990205315c76f3a704d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="f0725-102">Метод ICorDebugNativeFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="f0725-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="f0725-103">Возвращает значение HRESULT, указывающее, можно ли безопасно значение указателя инструкций (IP) заданное расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="f0725-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0725-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0725-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0725-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0725-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="f0725-106">[in] Нужное значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="f0725-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0725-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0725-107">Remarks</span></span>  
 <span data-ttu-id="f0725-108">Используйте `CanSetIP` метод до вызова метода [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f0725-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="f0725-109">Если `CanSetIP` возвращает любой HRESULT, отличных от S_OK, по-прежнему можно вызвать `ICorDebugNativeFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="f0725-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0725-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f0725-110">Requirements</span></span>  
 <span data-ttu-id="f0725-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0725-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0725-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0725-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0725-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0725-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0725-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0725-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0725-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f0725-115">See Also</span></span>  
 
