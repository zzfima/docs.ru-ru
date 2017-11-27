---
title: "Метод ICorDebugILFrame::GetLocalVariable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetLocalVariable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 24b4ed62c3fb68306683d2199f901ec510f0da6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="4d28d-102">Метод ICorDebugILFrame::GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="4d28d-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="4d28d-103">Получает значение указанной локальной переменной в кадре стека промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="4d28d-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d28d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d28d-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d28d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d28d-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="4d28d-106">[in] Индекс локальной переменной в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="4d28d-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="4d28d-107">[out] Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение.</span><span class="sxs-lookup"><span data-stu-id="4d28d-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d28d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d28d-108">Remarks</span></span>  
 <span data-ttu-id="4d28d-109">`GetLocalVariable` Метод может использоваться в кадре стека MSIL или в кадре скомпилированных just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="4d28d-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d28d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4d28d-110">Requirements</span></span>  
 <span data-ttu-id="4d28d-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d28d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d28d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d28d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d28d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d28d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d28d-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d28d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
