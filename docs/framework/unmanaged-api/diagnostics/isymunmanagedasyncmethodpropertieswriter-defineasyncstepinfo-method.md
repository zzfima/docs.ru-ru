---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8305d0a562fd90e3fae32e372b663ca3942d2a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080856"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="65599-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="65599-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="65599-103">Определить группу async await операций в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="65599-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="65599-104">Смещение каждого yield соответствует инструкции return оператором await, определение потенциальных yield.</span><span class="sxs-lookup"><span data-stu-id="65599-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="65599-105">Каждый `breakpointMethod` / `breakpointOffset` пары сообщает, где асинхронной операции будет возобновлена, который может быть в другом методе.</span><span class="sxs-lookup"><span data-stu-id="65599-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65599-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65599-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65599-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="65599-107">Parameters</span></span>  
  
|<span data-ttu-id="65599-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="65599-108">Parameter</span></span>|<span data-ttu-id="65599-109">Описание</span><span class="sxs-lookup"><span data-stu-id="65599-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="65599-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="65599-110">Return Value</span></span>  
 <span data-ttu-id="65599-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="65599-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65599-112">Требования</span><span class="sxs-lookup"><span data-stu-id="65599-112">Requirements</span></span>  
 <span data-ttu-id="65599-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="65599-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65599-114">См. также</span><span class="sxs-lookup"><span data-stu-id="65599-114">See also</span></span>

- [<span data-ttu-id="65599-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="65599-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
