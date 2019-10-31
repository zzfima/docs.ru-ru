---
title: Метод ICorDebugClass::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
ms.openlocfilehash: 94f2d20816bfc28118877f52c04237c41b3859e3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125788"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="8b621-102">Метод ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="8b621-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="8b621-103">Возвращает модуль, который определяет этот класс.</span><span class="sxs-lookup"><span data-stu-id="8b621-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b621-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b621-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b621-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b621-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="8b621-106">заполняет Указатель на адрес объекта ICorDebugModule, который представляет модуль, в котором определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="8b621-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b621-107">Требования</span><span class="sxs-lookup"><span data-stu-id="8b621-107">Requirements</span></span>  
 <span data-ttu-id="8b621-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b621-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b621-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b621-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b621-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b621-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b621-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b621-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
