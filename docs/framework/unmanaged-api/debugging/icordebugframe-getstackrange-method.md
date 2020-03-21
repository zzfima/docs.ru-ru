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
ms.openlocfilehash: 7a35ce025360e0ec8b7085d68e54548026b7c7fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178902"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="f9219-102">Метод ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="f9219-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="f9219-103">Получает абсолютный диапазон адресов этого стека кадра.</span><span class="sxs-lookup"><span data-stu-id="f9219-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9219-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9219-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9219-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9219-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="f9219-106">(ваут) Указатель на `CORDB_ADDRESS` указатель, который определяет начальный адрес кадра `ICorDebugFrame` стека, представленного этим объектом.</span><span class="sxs-lookup"><span data-stu-id="f9219-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="f9219-107">(ваут) Указатель на `CORDB_ADDRESS` указатель, который определяет конечный адрес кадра `ICorDebugFrame` стека, представленного этим объектом.</span><span class="sxs-lookup"><span data-stu-id="f9219-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9219-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9219-108">Remarks</span></span>  
 <span data-ttu-id="f9219-109">Диапазон адресов стека полезен для склеивания взаимосвязанных следов стека, собранных из нескольких двигателей отладки.</span><span class="sxs-lookup"><span data-stu-id="f9219-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="f9219-110">Числовой диапазон не содержит информации о содержимом кадра стека.</span><span class="sxs-lookup"><span data-stu-id="f9219-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="f9219-111">Это имеет смысл только для сравнения расположения стек кадра.</span><span class="sxs-lookup"><span data-stu-id="f9219-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9219-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f9219-112">Requirements</span></span>  
 <span data-ttu-id="f9219-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9219-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9219-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9219-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9219-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9219-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9219-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9219-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
