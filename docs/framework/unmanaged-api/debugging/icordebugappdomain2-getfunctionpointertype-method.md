---
title: Метод ICorDebugAppDomain2::GetFunctionPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec1a9968dbec10783c6f1383fb523e95ff79561e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61683917"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="6f6b1-102">Метод ICorDebugAppDomain2::GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="6f6b1-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="6f6b1-103">Получает указатель на функцию с заданной подписью.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f6b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f6b1-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f6b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f6b1-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="6f6b1-106">[in] Количество аргументов типа для функции.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="6f6b1-107">[in] Массив указателей, каждый из которых указывает ICorDebugType объект, представляющий аргумент типа функции.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="6f6b1-108">Первый элемент — тип возвращаемого значения; Каждый из остальных элементов является типом параметра.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="6f6b1-109">[out] Указатель на адрес `ICorDebugType` , представляющий указатель на функцию.</span><span class="sxs-lookup"><span data-stu-id="6f6b1-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f6b1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6f6b1-110">Requirements</span></span>  
 <span data-ttu-id="6f6b1-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f6b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f6b1-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f6b1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f6b1-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f6b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f6b1-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f6b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
