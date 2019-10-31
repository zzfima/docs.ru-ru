---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: 59e3a95a4d2573263600da60b4f852caa361138e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129197"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="f759a-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="f759a-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="f759a-103">Определите группу асинхронных операций await в текущем методе.</span><span class="sxs-lookup"><span data-stu-id="f759a-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="f759a-104">Каждое значение yield Offset соответствует инструкции Return, определяющей потенциальный доход.</span><span class="sxs-lookup"><span data-stu-id="f759a-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="f759a-105">Каждая пара `breakpointMethod`/`breakpointOffset` указывает, где будет возобновлена асинхронная операция, которая может быть в другом методе.</span><span class="sxs-lookup"><span data-stu-id="f759a-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f759a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f759a-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f759a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f759a-107">Parameters</span></span>  
  
|<span data-ttu-id="f759a-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="f759a-108">Parameter</span></span>|<span data-ttu-id="f759a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f759a-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="f759a-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f759a-110">Return Value</span></span>  
 <span data-ttu-id="f759a-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="f759a-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f759a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f759a-112">Requirements</span></span>  
 <span data-ttu-id="f759a-113">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f759a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f759a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f759a-114">See also</span></span>

- [<span data-ttu-id="f759a-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="f759a-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
