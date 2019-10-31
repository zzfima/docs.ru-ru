---
title: Метод ICorDebugFunction::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
ms.openlocfilehash: 887d207aea3de9296107c041816606b2f5947406
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124034"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="36b08-102">Метод ICorDebugFunction::GetClass</span><span class="sxs-lookup"><span data-stu-id="36b08-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="36b08-103">Возвращает объект ICorDebugClass, представляющий класс, членом которого является эта функция.</span><span class="sxs-lookup"><span data-stu-id="36b08-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36b08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36b08-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36b08-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36b08-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="36b08-106">заполняет Указатель на адрес объекта `ICorDebugClass`, который представляет класс, или значение null, если эта функция не является членом класса.</span><span class="sxs-lookup"><span data-stu-id="36b08-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36b08-107">Требования</span><span class="sxs-lookup"><span data-stu-id="36b08-107">Requirements</span></span>  
 <span data-ttu-id="36b08-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36b08-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36b08-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36b08-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36b08-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36b08-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36b08-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36b08-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
