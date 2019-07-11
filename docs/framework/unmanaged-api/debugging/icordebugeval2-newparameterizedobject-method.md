---
title: Метод ICorDebugEval2::NewParameterizedObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aae5f4c79acd6f92d42c2890ba64fa66e1b4bfbe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753588"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="ccabc-102">Метод ICorDebugEval2::NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="ccabc-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="ccabc-103">Создает новый объект параметризованного типа и вызывает метод-конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="ccabc-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccabc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccabc-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccabc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccabc-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="ccabc-106">[in] Указатель на объект ICorDebugFunction, представляющий конструктор для создания экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="ccabc-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="ccabc-107">[in] Передано число аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="ccabc-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="ccabc-108">[in] Массив указателей, каждый из которых указывает на объект, представляющий аргумент типа для объекта, экземпляр которого создается ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="ccabc-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="ccabc-109">[in] Число аргументов, переданных в конструктор.</span><span class="sxs-lookup"><span data-stu-id="ccabc-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="ccabc-110">[in] Массив указателей, каждый из которых указывает ICorDebugValue объект, представляющий значение аргумента, который передается в конструктор.</span><span class="sxs-lookup"><span data-stu-id="ccabc-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccabc-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ccabc-111">Remarks</span></span>  
 <span data-ttu-id="ccabc-112">Конструктор объекта может занять <xref:System.Type> параметров.</span><span class="sxs-lookup"><span data-stu-id="ccabc-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccabc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ccabc-113">Requirements</span></span>  
 <span data-ttu-id="ccabc-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccabc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccabc-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccabc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccabc-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccabc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccabc-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccabc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
