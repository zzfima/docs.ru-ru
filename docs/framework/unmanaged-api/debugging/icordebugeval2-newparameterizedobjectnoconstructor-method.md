---
title: Метод ICorDebugEval2::NewParameterizedObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4434f5d0eaa45c9cfcbadb20b29564f0643a2dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754443"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="a9c21-102">Метод ICorDebugEval2::NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="a9c21-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="a9c21-103">Создает новый объект параметризованного типа указанного класса не пытается вызвать метод-конструктор.</span><span class="sxs-lookup"><span data-stu-id="a9c21-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9c21-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9c21-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9c21-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="a9c21-106">[in] Указатель на объект ICorDebugClass, который представляет класс для создания экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="a9c21-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="a9c21-107">[in] Передано число аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="a9c21-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="a9c21-108">[in] Массив указателей, каждый из которых указывает на объект, представляющий аргумент типа для объекта, экземпляр которого создается ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="a9c21-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9c21-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9c21-109">Remarks</span></span>  
 <span data-ttu-id="a9c21-110">`NewParameterizedObjectNoConstructor` Метод завершится ошибкой, если неверное число аргументов типа, или неправильный типы аргументов типа передаются.</span><span class="sxs-lookup"><span data-stu-id="a9c21-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9c21-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a9c21-111">Requirements</span></span>  
 <span data-ttu-id="a9c21-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9c21-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9c21-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9c21-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9c21-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9c21-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9c21-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9c21-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
