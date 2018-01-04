---
title: "Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c33403c48e6f395d8d0e10c7fddcea327d87529a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="7d9ad-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="7d9ad-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="7d9ad-103">Определите группу async await операций в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="7d9ad-104">Смещение каждого yield соответствует инструкции return await, идентификации потенциальных yield.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="7d9ad-105">Каждый `breakpointMethod` / `breakpointOffset` пары показывает, где будет возобновлена асинхронную операцию, (который может быть в другом методе.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d9ad-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d9ad-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d9ad-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d9ad-107">Parameters</span></span>  
  
|<span data-ttu-id="7d9ad-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="7d9ad-108">Parameter</span></span>|<span data-ttu-id="7d9ad-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="7d9ad-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="7d9ad-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7d9ad-110">Return Value</span></span>  
 <span data-ttu-id="7d9ad-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d9ad-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7d9ad-112">Requirements</span></span>  
 <span data-ttu-id="7d9ad-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7d9ad-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d9ad-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7d9ad-114">See Also</span></span>  
 [<span data-ttu-id="7d9ad-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="7d9ad-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
