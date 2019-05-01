---
title: Метод ICorDebugEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d1226f64df379b5c40304221e9e66eebcdb17b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989135"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="2cdd4-102">Метод ICorDebugEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="2cdd4-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="2cdd4-103">Создает копию данного объекта ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="2cdd4-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cdd4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cdd4-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cdd4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2cdd4-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="2cdd4-106">[out] Указатель на адрес `ICorDebugEnum` объект, являющийся копией этого `ICorDebugEnum` объекта.</span><span class="sxs-lookup"><span data-stu-id="2cdd4-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cdd4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="2cdd4-107">Requirements</span></span>  
 <span data-ttu-id="2cdd4-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cdd4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cdd4-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cdd4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cdd4-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cdd4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cdd4-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cdd4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
