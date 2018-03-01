---
title: "Метод ICorDebugType::GetBase"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c28c88988155cf5e00897858d4306e4cb2ea78a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="634f5-102">Метод ICorDebugType::GetBase</span><span class="sxs-lookup"><span data-stu-id="634f5-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="634f5-103">Получает указатель интерфейса на ICorDebugType, представляющий базовый тип, при наличии такового типа, представленного этим экземпляром `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="634f5-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="634f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="634f5-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="634f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="634f5-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="634f5-106">[out] Указатель на адрес `ICorDebugType` , представляющий базовый тип.</span><span class="sxs-lookup"><span data-stu-id="634f5-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="634f5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="634f5-107">Remarks</span></span>  
 <span data-ttu-id="634f5-108">Поиск базового типа для типа полезен для реализации общей функциональности отладчика, например печати все поля объекта или его родительских классов.</span><span class="sxs-lookup"><span data-stu-id="634f5-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="634f5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="634f5-109">Requirements</span></span>  
 <span data-ttu-id="634f5-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="634f5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="634f5-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="634f5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="634f5-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="634f5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="634f5-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="634f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
