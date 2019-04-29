---
title: Метод ISymUnmanagedAsyncMethod::GetAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7c72d0766580f9aa3aa678aacd872b804172a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940222"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="858cd-102">Метод ISymUnmanagedAsyncMethod::GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="858cd-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="858cd-103">См. в разделе [метод DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="858cd-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="858cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="858cd-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="858cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="858cd-105">Parameters</span></span>  
  
|<span data-ttu-id="858cd-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="858cd-106">Parameter</span></span>|<span data-ttu-id="858cd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="858cd-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="858cd-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="858cd-108">Return Value</span></span>  
 <span data-ttu-id="858cd-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="858cd-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="858cd-110">Требования</span><span class="sxs-lookup"><span data-stu-id="858cd-110">Requirements</span></span>  
 <span data-ttu-id="858cd-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="858cd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="858cd-112">См. также</span><span class="sxs-lookup"><span data-stu-id="858cd-112">See also</span></span>

- [<span data-ttu-id="858cd-113">Интерфейс ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="858cd-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
