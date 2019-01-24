---
title: Метод ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a27a50e6fb120e537d28759a79a2b90c6d437e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600457"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="2e9b2-102">Метод ICorDebugNativeFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="2e9b2-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="2e9b2-103">Получает расположение, к которому в настоящее время задать указатель инструкций смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="2e9b2-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e9b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e9b2-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e9b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e9b2-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="2e9b2-106">[out] Указатель на расположение смещения в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="2e9b2-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e9b2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e9b2-107">Remarks</span></span>  
 <span data-ttu-id="2e9b2-108">Если кадр стека, представленного «ICorDebugNativeFrame» активен, значением offset является адрес следующую инструкцию для выполнения.</span><span class="sxs-lookup"><span data-stu-id="2e9b2-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="2e9b2-109">Если данный кадр стека не активен, смещение является адресом следующую инструкцию для выполнения при повторной активации кадра стека.</span><span class="sxs-lookup"><span data-stu-id="2e9b2-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e9b2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2e9b2-110">Requirements</span></span>  
 <span data-ttu-id="2e9b2-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e9b2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e9b2-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e9b2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e9b2-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e9b2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e9b2-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e9b2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9b2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2e9b2-115">See also</span></span>

