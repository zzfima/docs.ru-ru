---
title: Метод ICorDebugILFrame::GetArgument
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: 01c7cb2e4359a477c26f995602dbf29668e567c0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131013"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="a5a7b-102">Метод ICorDebugILFrame::GetArgument</span><span class="sxs-lookup"><span data-stu-id="a5a7b-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="a5a7b-103">Возвращает значение указанного аргумента в кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="a5a7b-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5a7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5a7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5a7b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5a7b-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="a5a7b-106">окне Индекс аргумента в этом кадре стека MSIL.</span><span class="sxs-lookup"><span data-stu-id="a5a7b-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a5a7b-107">заполняет Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение.</span><span class="sxs-lookup"><span data-stu-id="a5a7b-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5a7b-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="a5a7b-108">Remarks</span></span>  
 <span data-ttu-id="a5a7b-109">Метод `GetArgument` можно использовать либо в кадре стека MSIL, либо в кадре JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="a5a7b-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5a7b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a5a7b-110">Requirements</span></span>  
 <span data-ttu-id="a5a7b-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5a7b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5a7b-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5a7b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5a7b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5a7b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5a7b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5a7b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
