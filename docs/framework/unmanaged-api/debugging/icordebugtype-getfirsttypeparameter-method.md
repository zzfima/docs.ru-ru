---
title: Метод ICorDebugType::GetFirstTypeParameter
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: 1a02190b595fb01bdc2df46182bfa64bfe638db4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791280"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="47737-102">Метод ICorDebugType::GetFirstTypeParameter</span><span class="sxs-lookup"><span data-stu-id="47737-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="47737-103">Возвращает указатель интерфейса на объект ICorDebugType, представляющий первый параметр <xref:System.Type> типа, представленного этим `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="47737-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47737-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47737-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47737-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47737-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="47737-106">заполняет Указатель на адрес объекта `ICorDebugType`, представляющего первый параметр.</span><span class="sxs-lookup"><span data-stu-id="47737-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47737-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="47737-107">Remarks</span></span>  
 <span data-ttu-id="47737-108">`GetFirstTypeParameter` могут вызываться в случаях, когда дополнительные сведения о типе в большинстве случаев имеют один параметр типа.</span><span class="sxs-lookup"><span data-stu-id="47737-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="47737-109">В частности, его можно использовать, если тип является ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF или ELEMENT_TYPE_PTR, как показано в методе [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="47737-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47737-110">Требования</span><span class="sxs-lookup"><span data-stu-id="47737-110">Requirements</span></span>  
 <span data-ttu-id="47737-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47737-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47737-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47737-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47737-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47737-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47737-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47737-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
