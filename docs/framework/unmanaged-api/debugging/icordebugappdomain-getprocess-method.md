---
title: "Метод ICorDebugAppDomain::GetProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 27c092c029f259ed64eda26401bb9085f23d2bfa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="8bec6-102">Метод ICorDebugAppDomain::GetProcess</span><span class="sxs-lookup"><span data-stu-id="8bec6-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="8bec6-103">Получает процесс, содержащий домен приложения.</span><span class="sxs-lookup"><span data-stu-id="8bec6-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bec6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bec6-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bec6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bec6-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="8bec6-106">[out] Указатель на адрес объекта ICorDebugProcess, представляющего процесс.</span><span class="sxs-lookup"><span data-stu-id="8bec6-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bec6-107">Требования</span><span class="sxs-lookup"><span data-stu-id="8bec6-107">Requirements</span></span>  
 <span data-ttu-id="8bec6-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bec6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bec6-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bec6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bec6-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bec6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bec6-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bec6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
