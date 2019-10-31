---
title: Метод ICorDebugType::GetRank
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
ms.openlocfilehash: 9a00177faabfcad56d70ec5c64328c90675c1532
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138765"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="839ac-102">Метод ICorDebugType::GetRank</span><span class="sxs-lookup"><span data-stu-id="839ac-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="839ac-103">Возвращает число измерений в типе массива.</span><span class="sxs-lookup"><span data-stu-id="839ac-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="839ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="839ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="839ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="839ac-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="839ac-106">заполняет Указатель на число измерений.</span><span class="sxs-lookup"><span data-stu-id="839ac-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="839ac-107">Требования</span><span class="sxs-lookup"><span data-stu-id="839ac-107">Requirements</span></span>  
 <span data-ttu-id="839ac-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="839ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="839ac-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="839ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="839ac-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="839ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="839ac-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="839ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
