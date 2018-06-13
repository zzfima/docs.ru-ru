---
title: Метод ICorDebugAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84ca240f937e210846e6eb9a17abfe70a280b87d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403560"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="26eae-102">Метод ICorDebugAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="26eae-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="26eae-103">Возвращает заданное число доменов приложений из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="26eae-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26eae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26eae-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26eae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="26eae-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="26eae-106">[in] Число доменов приложений, должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="26eae-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="26eae-107">[out] Массив указателей, каждый из которых указывает на объект ICorDebugAppDomain, который представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="26eae-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="26eae-108">[out] Указатель на число фактически извлеченных доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="26eae-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="26eae-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="26eae-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26eae-110">Требования</span><span class="sxs-lookup"><span data-stu-id="26eae-110">Requirements</span></span>  
 <span data-ttu-id="26eae-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26eae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26eae-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26eae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26eae-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26eae-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26eae-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26eae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
