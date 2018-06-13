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
ms.openlocfilehash: ad1ea4da252fe9fac89faa79195b6a6de245ad9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414704"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="9f854-102">Метод ICorDebugILFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="9f854-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="9f854-103">Возвращает значение HRESULT, указывающее, можно ли безопасно значение указателя инструкций заданное расположение смещения в коде промежуточного языка Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="9f854-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f854-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f854-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f854-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f854-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="9f854-106">[in] Нужное значение указателя инструкций.</span><span class="sxs-lookup"><span data-stu-id="9f854-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f854-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f854-107">Remarks</span></span>  
 <span data-ttu-id="9f854-108">Используйте `CanSetIP` метод перед вызовом метода [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9f854-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="9f854-109">Если `CanSetIP` возвращает любой HRESULT, отличных от S_OK, по-прежнему можно вызвать `ICorDebugILFrame::SetIP`, но нет никакой гарантии, что отладчик продолжит выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="9f854-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f854-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9f854-110">Requirements</span></span>  
 <span data-ttu-id="9f854-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f854-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f854-112">**Заголовок:** CorDebug.idl CorDebug, h</span><span class="sxs-lookup"><span data-stu-id="9f854-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="9f854-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f854-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f854-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f854-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
