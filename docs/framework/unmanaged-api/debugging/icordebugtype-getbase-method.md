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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c24d6e9c42a091eafbe6d4bdee2bb4e055fd8852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772036"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="ddd0c-102">Метод ICorDebugType::GetBase</span><span class="sxs-lookup"><span data-stu-id="ddd0c-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="ddd0c-103">Получает указатель интерфейса на ICorDebugType, представляющей базовый тип, в том случае, если таковой имеется, типа, представленного этим объектом `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="ddd0c-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddd0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddd0c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddd0c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ddd0c-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="ddd0c-106">[out] Указатель на адрес `ICorDebugType` , представляющий базовый тип.</span><span class="sxs-lookup"><span data-stu-id="ddd0c-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddd0c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ddd0c-107">Remarks</span></span>  
 <span data-ttu-id="ddd0c-108">Поиск базового типа для типа полезен для реализации общей функциональности отладчика, такие как печать все поля объекта или его родительских классов.</span><span class="sxs-lookup"><span data-stu-id="ddd0c-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddd0c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ddd0c-109">Requirements</span></span>  
 <span data-ttu-id="ddd0c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddd0c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddd0c-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddd0c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddd0c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddd0c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddd0c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddd0c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
