---
title: Метод ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5da87071bc23ac17a3077049cd77f0fb8611439f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413024"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="c1c43-102">Метод ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="c1c43-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="c1c43-103">Возвращает диапазон абсолютных адресов данного кадра стека.</span><span class="sxs-lookup"><span data-stu-id="c1c43-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1c43-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1c43-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1c43-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="c1c43-106">[out] Указатель на `CORDB_ADDRESS` , определяет начальный адрес кадра стека, представленный этим `ICorDebugFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="c1c43-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="c1c43-107">[out] Указатель на `CORDB_ADDRESS` , указывающий конечный адрес кадра стека, представленный этим `ICorDebugFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="c1c43-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1c43-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1c43-108">Remarks</span></span>  
 <span data-ttu-id="c1c43-109">Диапазон адресов стека полезен для комбинирования трассировок стека с чередованием, собранных из нескольких ядра отладки.</span><span class="sxs-lookup"><span data-stu-id="c1c43-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="c1c43-110">Числовой диапазон не предоставляет сведения о содержимом кадра стека.</span><span class="sxs-lookup"><span data-stu-id="c1c43-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="c1c43-111">Это значение только для сравнения расположений кадров стека.</span><span class="sxs-lookup"><span data-stu-id="c1c43-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c43-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c1c43-112">Requirements</span></span>  
 <span data-ttu-id="c1c43-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1c43-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c43-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1c43-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1c43-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1c43-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1c43-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c43-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
