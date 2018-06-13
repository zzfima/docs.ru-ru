---
title: Метод ICorDebugCode::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2de22729fd3d7a511c1105ebf810d0402bd73a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402087"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="51ce4-102">Метод ICorDebugCode::GetAddress</span><span class="sxs-lookup"><span data-stu-id="51ce4-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="51ce4-103">Получает относительный виртуальный адрес (RVA) сегмента кода, представляющий этот интерфейс «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="51ce4-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ce4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51ce4-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51ce4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51ce4-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="51ce4-106">[out] Указатель на относительный виртуальный адрес сегмента кода.</span><span class="sxs-lookup"><span data-stu-id="51ce4-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ce4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="51ce4-107">Requirements</span></span>  
 <span data-ttu-id="51ce4-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51ce4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ce4-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51ce4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51ce4-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51ce4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51ce4-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ce4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ce4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="51ce4-112">See Also</span></span>  
 
