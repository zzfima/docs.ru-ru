---
title: Метод ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: cff527aa7cde6a13667d47d030a0ef7db96ad5ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122337"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="83700-102">Метод ICorDebugType::GetBase</span><span class="sxs-lookup"><span data-stu-id="83700-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="83700-103">Возвращает указатель интерфейса на объект ICorDebugType, представляющий базовый тип, если он существует, типа, представленного этим `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="83700-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83700-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83700-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83700-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83700-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="83700-106">заполняет Указатель на адрес объекта `ICorDebugType`, который представляет базовый тип.</span><span class="sxs-lookup"><span data-stu-id="83700-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83700-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="83700-107">Remarks</span></span>  
 <span data-ttu-id="83700-108">Поиск базового типа для типа полезен для реализации общих функциональных возможностей отладчика, таких как вывод всех полей объекта или его родительских классов.</span><span class="sxs-lookup"><span data-stu-id="83700-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83700-109">Требования</span><span class="sxs-lookup"><span data-stu-id="83700-109">Requirements</span></span>  
 <span data-ttu-id="83700-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83700-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83700-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83700-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83700-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83700-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83700-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83700-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
