---
title: Метод ICorDebugCode::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c5d42aa7053c1138808775a16d820d5fef3b095
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410823"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="d9f18-102">Метод ICorDebugCode::GetSize</span><span class="sxs-lookup"><span data-stu-id="d9f18-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="d9f18-103">Возвращает размер в байтах двоичного кода, представленного «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="d9f18-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9f18-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9f18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9f18-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="d9f18-106">[out] Указатель на размер в байтах двоичного кода, который `ICorDebugCode` представляет.</span><span class="sxs-lookup"><span data-stu-id="d9f18-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9f18-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d9f18-107">Requirements</span></span>  
 <span data-ttu-id="d9f18-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9f18-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9f18-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9f18-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9f18-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9f18-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9f18-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9f18-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f18-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d9f18-112">See Also</span></span>  
 
