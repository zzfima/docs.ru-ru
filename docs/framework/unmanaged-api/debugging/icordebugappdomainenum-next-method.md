---
title: "Метод ICorDebugAppDomainEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomainEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c5b773cf49ed67ce6d5981650f2409f7860391a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="57267-102">Метод ICorDebugAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="57267-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="57267-103">Возвращает заданное число доменов приложений из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="57267-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57267-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57267-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57267-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57267-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="57267-106">[in] Число доменов приложений, должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="57267-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="57267-107">[out] Массив указателей, каждый из которых указывает на объект ICorDebugAppDomain, который представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="57267-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="57267-108">[out] Указатель на число фактически извлеченных доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="57267-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="57267-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="57267-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57267-110">Требования</span><span class="sxs-lookup"><span data-stu-id="57267-110">Requirements</span></span>  
 <span data-ttu-id="57267-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57267-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57267-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57267-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57267-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57267-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57267-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57267-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
