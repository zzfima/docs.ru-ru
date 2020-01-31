---
title: Метод ICorDebugType::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: 25ffbf73fbefbb3c584450283c3080dfc11ee598
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791243"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="9e11f-102">Метод ICorDebugType::GetType</span><span class="sxs-lookup"><span data-stu-id="9e11f-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="9e11f-103">Возвращает значение Корелементтипе, которое описывает собственный тип <xref:System.Type> среды CLR, представленный этим объектом ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="9e11f-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e11f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e11f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e11f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e11f-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="9e11f-106">заполняет Указатель на значение перечисления `CorElementType`, указывающее <xref:System.Type> среды CLR, которую представляет этот `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="9e11f-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e11f-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="9e11f-107">Remarks</span></span>  
 <span data-ttu-id="9e11f-108">Если значение `ty` является ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, можно вызвать метод [ICorDebugType::-Class](icordebugtype-getclass-method.md) , чтобы получить неэкземплярный тип для универсального типа. в противном случае не вызывайте `ICorDebugType::GetClass`.</span><span class="sxs-lookup"><span data-stu-id="9e11f-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e11f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9e11f-109">Requirements</span></span>  
 <span data-ttu-id="9e11f-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e11f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e11f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e11f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e11f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e11f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e11f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e11f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
