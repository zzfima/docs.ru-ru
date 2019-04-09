---
title: Метод ICorDebugCode::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0104a52c3aa206f86daff30d9d16298e6beae324
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099460"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="000fe-102">Метод ICorDebugCode::GetFunction</span><span class="sxs-lookup"><span data-stu-id="000fe-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="000fe-103">Возвращает «ICorDebugFunction», связанный с «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="000fe-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="000fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="000fe-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="000fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="000fe-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="000fe-106">[out] Указатель на адрес функции.</span><span class="sxs-lookup"><span data-stu-id="000fe-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="000fe-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="000fe-107">Remarks</span></span>  
 `ICorDebugCode` <span data-ttu-id="000fe-108">и `ICorDebugFunction` Ведение взаимно-однозначной связи.</span><span class="sxs-lookup"><span data-stu-id="000fe-108">and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="000fe-109">Требования</span><span class="sxs-lookup"><span data-stu-id="000fe-109">Requirements</span></span>  
 <span data-ttu-id="000fe-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="000fe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="000fe-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="000fe-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="000fe-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="000fe-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="000fe-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="000fe-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="000fe-114">См. также</span><span class="sxs-lookup"><span data-stu-id="000fe-114">See also</span></span>
