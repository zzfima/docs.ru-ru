---
title: Метод ICorDebugAppDomain::GetId
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
ms.openlocfilehash: 87c43d6f05dffbf10ca1dd9253abfe893db9adf5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110482"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="98536-102">Метод ICorDebugAppDomain::GetId</span><span class="sxs-lookup"><span data-stu-id="98536-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="98536-103">Возвращает уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="98536-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98536-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98536-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98536-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98536-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="98536-106">заполняет Уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="98536-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98536-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="98536-107">Remarks</span></span>  
 <span data-ttu-id="98536-108">Идентификатор домена приложения уникален в пределах содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="98536-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98536-109">Требования</span><span class="sxs-lookup"><span data-stu-id="98536-109">Requirements</span></span>  
 <span data-ttu-id="98536-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98536-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98536-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98536-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98536-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98536-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98536-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98536-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
