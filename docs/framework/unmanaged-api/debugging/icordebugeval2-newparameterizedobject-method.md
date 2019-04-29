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
ms.openlocfilehash: c35baaee13782566c64dd8447c6a034f699b5cd0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667006"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="eaf1f-102">Метод ICorDebugEval2::NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="eaf1f-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="eaf1f-103">Создает новый объект параметризованного типа и вызывает метод-конструктор объекта.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eaf1f-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaf1f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eaf1f-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="eaf1f-106">[in] Указатель на объект ICorDebugFunction, представляющий конструктор для создания экземпляра объекта.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="eaf1f-107">[in] Передано число аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="eaf1f-108">[in] Массив указателей, каждый из которых указывает на объект, представляющий аргумент типа для объекта, экземпляр которого создается ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="eaf1f-109">[in] Число аргументов, переданных в конструктор.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="eaf1f-110">[in] Массив указателей, каждый из которых указывает ICorDebugValue объект, представляющий значение аргумента, который передается в конструктор.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaf1f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="eaf1f-111">Remarks</span></span>  
 <span data-ttu-id="eaf1f-112">Конструктор объекта может занять <xref:System.Type> параметров.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaf1f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="eaf1f-113">Requirements</span></span>  
 <span data-ttu-id="eaf1f-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaf1f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf1f-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eaf1f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eaf1f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eaf1f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eaf1f-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf1f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
