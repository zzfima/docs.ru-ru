---
title: "Метод ICorDebugAppDomain2::GetArrayOrPointerType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2.GetArrayOrPointerType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c08a56ff7f6bd109c5568a7f992850708a22a4b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="2b5a9-102">Метод ICorDebugAppDomain2::GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="2b5a9-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="2b5a9-103">Возвращает массив указанного типа, указатель или ссылку на указанный тип.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b5a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b5a9-104">Syntax</span></span>  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b5a9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b5a9-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="2b5a9-106">[in] Значение CorElementType перечисление, указывающее базовый собственный тип (массив, указатель или ссылка) должен быть создан.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="2b5a9-107">[in] Ранг (то есть число измерений) массива.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="2b5a9-108">Это значение должно быть 0, если `elementType` указывает тип указателя или ссылки.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="2b5a9-109">[in] Указатель на объект ICorDebugType, представляющий тип массива, указателя или ссылки должен быть создан.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="2b5a9-110">[out] Указатель на адрес `ICorDebugType` тип, представляющий сконструированный массива, тип указателя или ссылки.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b5a9-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b5a9-111">Remarks</span></span>  
 <span data-ttu-id="2b5a9-112">Значение *elementType* должен быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="2b5a9-112">The value of *elementType* must be one of the following:</span></span>  
  
-   <span data-ttu-id="2b5a9-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="2b5a9-113">ELEMENT_TYPE_PTR</span></span>  
  
-   <span data-ttu-id="2b5a9-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="2b5a9-114">ELEMENT_TYPE_BYREF</span></span>  
  
-   <span data-ttu-id="2b5a9-115">ELEMENT_TYPE_ARRAY или ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="2b5a9-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="2b5a9-116">Если значение *elementType* ELEMENT_TYPE_PTR или ELEMENT_TYPE_BYREF, *nRank* должен быть равен нулю.</span><span class="sxs-lookup"><span data-stu-id="2b5a9-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b5a9-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2b5a9-117">Requirements</span></span>  
 <span data-ttu-id="2b5a9-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b5a9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b5a9-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b5a9-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b5a9-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b5a9-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b5a9-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b5a9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
