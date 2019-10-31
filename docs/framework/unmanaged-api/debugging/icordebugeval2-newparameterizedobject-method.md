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
ms.openlocfilehash: 5d01ab0b6b5d489b2181056129e22661a50108a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084845"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="0da3a-102">Метод ICorDebugEval2::NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="0da3a-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="0da3a-103">Создает новый объект параметризованного типа и вызывает метод конструктора объекта.</span><span class="sxs-lookup"><span data-stu-id="0da3a-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0da3a-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0da3a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0da3a-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="0da3a-106">окне Указатель на объект ICorDebugFunction, представляющий конструктор объекта, для которого создается экземпляр.</span><span class="sxs-lookup"><span data-stu-id="0da3a-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="0da3a-107">окне Число переданных аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="0da3a-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="0da3a-108">окне Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент типа для объекта, для которого создается экземпляр.</span><span class="sxs-lookup"><span data-stu-id="0da3a-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="0da3a-109">окне Число аргументов, переданных конструктору.</span><span class="sxs-lookup"><span data-stu-id="0da3a-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="0da3a-110">окне Массив указателей, каждый из которых указывает на объект ICorDebugValue, представляющий значение аргумента, передаваемое конструктору.</span><span class="sxs-lookup"><span data-stu-id="0da3a-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0da3a-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="0da3a-111">Remarks</span></span>  
 <span data-ttu-id="0da3a-112">Конструктор объекта может принимать <xref:System.Type> параметры.</span><span class="sxs-lookup"><span data-stu-id="0da3a-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da3a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0da3a-113">Requirements</span></span>  
 <span data-ttu-id="0da3a-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0da3a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da3a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0da3a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0da3a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0da3a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0da3a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da3a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
