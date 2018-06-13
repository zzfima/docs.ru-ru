---
title: Метод ICLRDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4ce7b90b417e0126337283ff16790f136cb16fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407692"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="ce9e7-102">Метод ICLRDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="ce9e7-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="ce9e7-103">Получает текущий контекст выполнения для данного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="ce9e7-104">Этот метод вызывается службами доступа к данным среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce9e7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce9e7-105">Syntax</span></span>  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce9e7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce9e7-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="ce9e7-107">[in] Идентификатор потока в целевом процессе операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="ce9e7-108">[in] Флаги, определяющие, какие части контекста следует возвращать.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="ce9e7-109">Реализация возвратит, по крайней мере эти части контекста.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="ce9e7-110">[in] Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="ce9e7-111">[out] Указатель на буфер, в который следует поместить в контекст.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="ce9e7-112">Данные в `context` буфера должен быть в формате Win32 `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="ce9e7-113">Контекст задает данные от процессора регистра, поэтому определение Win32 `CONTEXT` структура зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="ce9e7-114">Ссылаться на файл заголовка WinNT.h, для определения Win32 `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce9e7-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce9e7-115">Remarks</span></span>  
 <span data-ttu-id="ce9e7-116">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="ce9e7-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce9e7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="ce9e7-117">Requirements</span></span>  
 <span data-ttu-id="ce9e7-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce9e7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce9e7-119">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="ce9e7-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ce9e7-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce9e7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce9e7-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce9e7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce9e7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ce9e7-122">See Also</span></span>  
 [<span data-ttu-id="ce9e7-123">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="ce9e7-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
