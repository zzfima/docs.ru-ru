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
ms.openlocfilehash: aad5a285fc2280dc062b0f4cbb69977a7e605e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412773"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="2f367-102">Метод ICorDebugEval2::NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="2f367-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="2f367-103">Создает новый объект параметризованного типа указанного класса без попытки вызова метода конструктора.</span><span class="sxs-lookup"><span data-stu-id="2f367-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f367-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f367-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f367-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f367-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="2f367-106">[in] Указатель на объект ICorDebugClass, который представляет класс для создания экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="2f367-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="2f367-107">[in] Число аргументов типа передано.</span><span class="sxs-lookup"><span data-stu-id="2f367-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="2f367-108">[in] Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент типа для объекта, экземпляр которого создается.</span><span class="sxs-lookup"><span data-stu-id="2f367-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f367-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f367-109">Remarks</span></span>  
 <span data-ttu-id="2f367-110">`NewParameterizedObjectNoConstructor` Метод завершится ошибкой, если неверное количество аргументов-типов или передаются неправильный типы аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="2f367-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f367-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2f367-111">Requirements</span></span>  
 <span data-ttu-id="2f367-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f367-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f367-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f367-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f367-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f367-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f367-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f367-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
