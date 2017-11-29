---
title: "Метод ICorDebugCode::GetSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94c530015cc1770adf31c336dfb00eb06ffd70a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="93057-102">Метод ICorDebugCode::GetSize</span><span class="sxs-lookup"><span data-stu-id="93057-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="93057-103">Возвращает размер в байтах двоичного кода, представленного «ICorDebugCode».</span><span class="sxs-lookup"><span data-stu-id="93057-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93057-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93057-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93057-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93057-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="93057-106">[out] Указатель на размер в байтах двоичного кода, который `ICorDebugCode` представляет.</span><span class="sxs-lookup"><span data-stu-id="93057-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93057-107">Требования</span><span class="sxs-lookup"><span data-stu-id="93057-107">Requirements</span></span>  
 <span data-ttu-id="93057-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93057-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93057-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93057-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93057-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93057-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93057-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93057-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93057-112">См. также</span><span class="sxs-lookup"><span data-stu-id="93057-112">See Also</span></span>  
 
