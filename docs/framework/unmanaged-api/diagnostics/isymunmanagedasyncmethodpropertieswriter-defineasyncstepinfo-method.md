---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ebd4bb1d674a27785ccbe5460a65fed764638ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435881"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="0c8e5-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="0c8e5-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="0c8e5-103">Определите группу async await операций в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="0c8e5-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="0c8e5-104">Смещение каждого yield соответствует инструкции return await, идентификации потенциальных yield.</span><span class="sxs-lookup"><span data-stu-id="0c8e5-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="0c8e5-105">Каждый `breakpointMethod` / `breakpointOffset` пары показывает, где будет возобновлена асинхронную операцию, (который может быть в другом методе.</span><span class="sxs-lookup"><span data-stu-id="0c8e5-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8e5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c8e5-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c8e5-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c8e5-107">Parameters</span></span>  
  
|<span data-ttu-id="0c8e5-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="0c8e5-108">Parameter</span></span>|<span data-ttu-id="0c8e5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0c8e5-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="0c8e5-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0c8e5-110">Return Value</span></span>  
 <span data-ttu-id="0c8e5-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="0c8e5-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c8e5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0c8e5-112">Requirements</span></span>  
 <span data-ttu-id="0c8e5-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0c8e5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8e5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0c8e5-114">See Also</span></span>  
 [<span data-ttu-id="0c8e5-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="0c8e5-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
