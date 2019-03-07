---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bac541909e07aadff06006fba8c3cfcf4dc5465
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486229"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="57470-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="57470-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="57470-103">Определить группу async await операций в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="57470-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="57470-104">Смещение каждого yield соответствует инструкции return оператором await, определение потенциальных yield.</span><span class="sxs-lookup"><span data-stu-id="57470-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="57470-105">Каждый `breakpointMethod` / `breakpointOffset` пары сообщает, где асинхронной операции будет возобновлена, который может быть в другом методе.</span><span class="sxs-lookup"><span data-stu-id="57470-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57470-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57470-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57470-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="57470-107">Parameters</span></span>  
  
|<span data-ttu-id="57470-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="57470-108">Parameter</span></span>|<span data-ttu-id="57470-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="57470-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="57470-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="57470-110">Return Value</span></span>  
 <span data-ttu-id="57470-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="57470-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57470-112">Требования</span><span class="sxs-lookup"><span data-stu-id="57470-112">Requirements</span></span>  
 <span data-ttu-id="57470-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="57470-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57470-114">См. также</span><span class="sxs-lookup"><span data-stu-id="57470-114">See also</span></span>
- [<span data-ttu-id="57470-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="57470-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
