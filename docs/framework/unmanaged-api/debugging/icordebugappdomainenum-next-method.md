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
ms.openlocfilehash: 10d53ebac99942ac9376041f217df53965bdbb2f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="f8a8d-102">Метод ICorDebugAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="f8a8d-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="f8a8d-103">Возвращает заданное число доменов приложений из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="f8a8d-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8a8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8a8d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8a8d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8a8d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f8a8d-106">[in] Число доменов приложений, должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="f8a8d-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="f8a8d-107">[out] Массив указателей, каждый из которых указывает на объект ICorDebugAppDomain, который представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="f8a8d-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f8a8d-108">[out] Указатель на число фактически извлеченных доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="f8a8d-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="f8a8d-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="f8a8d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8a8d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f8a8d-110">Requirements</span></span>  
 <span data-ttu-id="f8a8d-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8a8d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8a8d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8a8d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8a8d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8a8d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8a8d-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8a8d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
