---
title: Метод ICorDebugThread::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: d1b058aef66ed32c2cadcc3cfd72320dd8eb7729
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133597"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="72c01-102">Метод ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="72c01-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="72c01-103">Создает объект ICorDebugStepper, позволяющий выполнять пошаговую отладку активной рамки этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="72c01-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72c01-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72c01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="72c01-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="72c01-106">заполняет Указатель на адрес объекта `ICorDebugStepper`, который позволяет пошагово пройти по активному кадру этого потока.</span><span class="sxs-lookup"><span data-stu-id="72c01-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72c01-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="72c01-107">Remarks</span></span>  
 <span data-ttu-id="72c01-108">Активным кадром может быть неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="72c01-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="72c01-109">Для выполнения фактического пошагового шага необходимо использовать интерфейс `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="72c01-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72c01-110">Требования</span><span class="sxs-lookup"><span data-stu-id="72c01-110">Requirements</span></span>  
 <span data-ttu-id="72c01-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72c01-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72c01-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72c01-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72c01-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72c01-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72c01-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72c01-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
