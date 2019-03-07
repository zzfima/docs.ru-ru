---
title: Метод ICorDebugType::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8fa39a54437e60737aa052c495f58422bc0d3fe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474453"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a><span data-ttu-id="74a66-102">Метод ICorDebugType::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="74a66-102">ICorDebugType::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="74a66-103">Получает указатель интерфейса на ICorDebugTypeEnum, который содержит <xref:System.Type> параметры типа класса, который ссылается этот ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="74a66-103">Gets an interface pointer to an ICorDebugTypeEnum that contains the <xref:System.Type> parameters of the class referenced by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74a66-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74a66-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="74a66-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="74a66-106">[out] Указатель на адрес `ICorDebugTypeEnum` , содержащий параметры типа.</span><span class="sxs-lookup"><span data-stu-id="74a66-106">[out] A pointer to the address of an `ICorDebugTypeEnum` that contains the parameters of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74a66-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="74a66-107">Remarks</span></span>  
 <span data-ttu-id="74a66-108">Можно использовать `EnumerateTypeParameters` Если CorElementType значение, возвращаемое функцией [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR или ELEMENT_TYPE_FNPTR.</span><span class="sxs-lookup"><span data-stu-id="74a66-108">You can use `EnumerateTypeParameters` if the CorElementType value returned by [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) is ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR, or ELEMENT_TYPE_FNPTR.</span></span> <span data-ttu-id="74a66-109">Число параметров и их порядок зависит от типа:</span><span class="sxs-lookup"><span data-stu-id="74a66-109">The number of parameters and their order depends on the type:</span></span>  
  
-   <span data-ttu-id="74a66-110">ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE: Число параметров типа, содержащихся в `ICorDebugTypeEnum` , этот метод возвращает, будет зависеть от числа типов формальных параметров для соответствующего класса.</span><span class="sxs-lookup"><span data-stu-id="74a66-110">ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE: The number of type parameters contained in the `ICorDebugTypeEnum` that this method returns, will depend on the number of formal type parameters for the corresponding class.</span></span> <span data-ttu-id="74a66-111">Например, если тип является `class Dict<String,int32>`, затем `EnumerateTypeParameters` вернет `ICorDebugTypeEnum` , содержащий объекты, представляющие `String` и `int32` в последовательности.</span><span class="sxs-lookup"><span data-stu-id="74a66-111">For example, if the type is `class Dict<String,int32>`, then `EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains objects representing `String` and `int32` in sequence.</span></span>  
  
-   <span data-ttu-id="74a66-112">ELEMENT_TYPE_FNPTR: Число параметров типа, содержащихся в `ICorDebugTypeEnum` будет иметь одно больше, чем число аргументов в объявлении функции.</span><span class="sxs-lookup"><span data-stu-id="74a66-112">ELEMENT_TYPE_FNPTR: The number of type parameters contained in the `ICorDebugTypeEnum` will be one greater than the number of arguments accepted by the function.</span></span> <span data-ttu-id="74a66-113">Первый параметр типа, содержащихся в `ICorDebugTypeEnum` тип возвращаемого значения для функции, и следующие параметры типа параметров функции.</span><span class="sxs-lookup"><span data-stu-id="74a66-113">The first type parameter contained in the `ICorDebugTypeEnum` is the return type for the function, and the subsequent type parameters are the function's parameters.</span></span>  
  
-   <span data-ttu-id="74a66-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF или ELEMENT_TYPE_PTR: Один параметр типа будет возвращаться.</span><span class="sxs-lookup"><span data-stu-id="74a66-114">ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR: One type parameter will be returned.</span></span> <span data-ttu-id="74a66-115">Например, если тип является типом массива, такие как `int32[]`,`EnumerateTypeParameters` вернет `ICorDebugTypeEnum` , содержащий объект, представляющий `int32`.</span><span class="sxs-lookup"><span data-stu-id="74a66-115">For example, if the type is an array type such as `int32[]`,`EnumerateTypeParameters` will return an `ICorDebugTypeEnum` that contains an object representing `int32`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74a66-116">Требования</span><span class="sxs-lookup"><span data-stu-id="74a66-116">Requirements</span></span>  
 <span data-ttu-id="74a66-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74a66-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74a66-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74a66-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74a66-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74a66-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74a66-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74a66-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
