---
title: "Метод ICorDebugEnum::Clone"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum.Clone
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ddd7d82b6eb2944b1d2a5d7a83f0ccc9f255e45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="d9ad3-102">Метод ICorDebugEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="d9ad3-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="d9ad3-103">Создает копию этого объекта ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="d9ad3-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ad3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9ad3-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9ad3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9ad3-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="d9ad3-106">[out] Указатель на адрес `ICorDebugEnum` объект, являющийся копией этого `ICorDebugEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="d9ad3-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ad3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d9ad3-107">Requirements</span></span>  
 <span data-ttu-id="d9ad3-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9ad3-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9ad3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9ad3-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9ad3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9ad3-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9ad3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
