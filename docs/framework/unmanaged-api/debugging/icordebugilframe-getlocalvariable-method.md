---
title: Метод ICorDebugILFrame::GetLocalVariable
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebd36f01297f24c050f84fb67e7673f8641fe206
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475246"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="d458f-102">Метод ICorDebugILFrame::GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="d458f-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="d458f-103">Получает значение указанной локальной переменной в кадре стека промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="d458f-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d458f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d458f-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d458f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d458f-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="d458f-106">[in] Индекс локальной переменной в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="d458f-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d458f-107">[out] Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение.</span><span class="sxs-lookup"><span data-stu-id="d458f-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d458f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d458f-108">Remarks</span></span>  
 <span data-ttu-id="d458f-109">`GetLocalVariable` Метод может использоваться в кадре стека MSIL или во фрейме скомпилированного just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="d458f-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d458f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d458f-110">Requirements</span></span>  
 <span data-ttu-id="d458f-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d458f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d458f-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d458f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d458f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d458f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d458f-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d458f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
