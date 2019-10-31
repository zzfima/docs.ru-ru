---
title: Метод ICorDebugAppDomain2::GetArrayOrPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
ms.openlocfilehash: 166f6bb50849df8550871958d7034fdf2a841abb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089114"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="a7203-102">Метод ICorDebugAppDomain2::GetArrayOrPointerType</span><span class="sxs-lookup"><span data-stu-id="a7203-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="a7203-103">Возвращает массив указанного типа или указатель или ссылку на указанный тип.</span><span class="sxs-lookup"><span data-stu-id="a7203-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7203-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7203-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7203-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7203-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="a7203-106">окне Значение перечисления Корелементтипе, которое указывает базовый собственный тип (массив, указатель или ссылка), который необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="a7203-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="a7203-107">окне Ранг (то есть количество измерений) массива.</span><span class="sxs-lookup"><span data-stu-id="a7203-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="a7203-108">Это значение должно быть равно 0, если `elementType` задает указатель или ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="a7203-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="a7203-109">окне Указатель на объект ICorDebugType, представляющий тип создаваемого массива, указателя или ссылки.</span><span class="sxs-lookup"><span data-stu-id="a7203-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="a7203-110">заполняет Указатель на адрес объекта `ICorDebugType`, представляющего сконструированный массив, тип указателя или ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="a7203-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7203-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="a7203-111">Remarks</span></span>  
 <span data-ttu-id="a7203-112">Значение *ElementType* должно быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="a7203-112">The value of *elementType* must be one of the following:</span></span>  
  
- <span data-ttu-id="a7203-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="a7203-113">ELEMENT_TYPE_PTR</span></span>  
  
- <span data-ttu-id="a7203-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="a7203-114">ELEMENT_TYPE_BYREF</span></span>  
  
- <span data-ttu-id="a7203-115">ELEMENT_TYPE_ARRAY или ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="a7203-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="a7203-116">Если значение *ElementType* — ELEMENT_TYPE_PTR или ELEMENT_TYPE_BYREF, *нранк* должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a7203-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7203-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a7203-117">Requirements</span></span>  
 <span data-ttu-id="a7203-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7203-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7203-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7203-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7203-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7203-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7203-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7203-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
