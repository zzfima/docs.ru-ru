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
ms.openlocfilehash: 85f06b49aab1f1d1745bd7e359ed311c2ba1e44d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130982"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="bc9cf-102">Метод ICorDebugILFrame::GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="bc9cf-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="bc9cf-103">Возвращает значение указанной локальной переменной в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="bc9cf-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc9cf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc9cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc9cf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc9cf-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="bc9cf-106">окне Индекс локальной переменной в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="bc9cf-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="bc9cf-107">заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение.</span><span class="sxs-lookup"><span data-stu-id="bc9cf-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc9cf-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="bc9cf-108">Remarks</span></span>  
 <span data-ttu-id="bc9cf-109">Метод `GetLocalVariable` можно использовать либо в кадре стека MSIL, либо в кадре JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="bc9cf-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc9cf-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bc9cf-110">Requirements</span></span>  
 <span data-ttu-id="bc9cf-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc9cf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc9cf-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc9cf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc9cf-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc9cf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc9cf-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc9cf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
