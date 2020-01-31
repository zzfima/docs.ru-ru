---
title: Метод ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791298"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="64e4b-102">Метод ICorDebugType::GetClass</span><span class="sxs-lookup"><span data-stu-id="64e4b-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="64e4b-103">Возвращает указатель интерфейса на объект ICorDebugClass, представляющий универсальный тип, экземпляр которого не был создан.</span><span class="sxs-lookup"><span data-stu-id="64e4b-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64e4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64e4b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64e4b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64e4b-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="64e4b-106">заполняет Указатель на адрес интерфейса `ICorDebugClass`, представляющий универсальный тип, экземпляр которого не был создан.</span><span class="sxs-lookup"><span data-stu-id="64e4b-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64e4b-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="64e4b-107">Remarks</span></span>  
 <span data-ttu-id="64e4b-108">`GetClass` могут вызываться только при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="64e4b-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="64e4b-109">Вызовите метод [ICorDebugType:: GetType](icordebugtype-gettype-method.md) перед вызовом `GetClass`.</span><span class="sxs-lookup"><span data-stu-id="64e4b-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="64e4b-110">Если `ICorDebugType::GetType` возвращает значение Корелементтипе, которое является ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, можно вызвать `GetClass`, чтобы получить неэкземплярный тип для универсального типа.</span><span class="sxs-lookup"><span data-stu-id="64e4b-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64e4b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="64e4b-111">Requirements</span></span>  
 <span data-ttu-id="64e4b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64e4b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64e4b-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64e4b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64e4b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64e4b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64e4b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64e4b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
