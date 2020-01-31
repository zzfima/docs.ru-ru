---
title: Метод ICLRDataTarget::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: cdf5776e1ac9907e63aba0e0d400e48aff683d51
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785300"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="c8684-102">Метод ICLRDataTarget::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="c8684-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="c8684-103">Задает текущий контекст указанного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="c8684-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="c8684-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c8684-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8684-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8684-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8684-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c8684-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c8684-107">окне Идентификатор операционной системы потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="c8684-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c8684-108">окне Размер контекста.</span><span class="sxs-lookup"><span data-stu-id="c8684-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="c8684-109">окне Указатель на буфер, содержащий контекст.</span><span class="sxs-lookup"><span data-stu-id="c8684-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="c8684-110">Данные в буфере `context` будут в формате структуры `CONTEXT` Win32.</span><span class="sxs-lookup"><span data-stu-id="c8684-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="c8684-111">Контекст задает зависящие от процессора данные регистра, поэтому определение структуры `CONTEXT` Win32 зависит от архитектуры процессора.</span><span class="sxs-lookup"><span data-stu-id="c8684-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="c8684-112">Описание структуры `CONTEXT` Win32 см. в файле заголовка WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="c8684-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8684-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="c8684-113">Remarks</span></span>  
 <span data-ttu-id="c8684-114">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="c8684-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8684-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c8684-115">Requirements</span></span>  
 <span data-ttu-id="c8684-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8684-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8684-117">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="c8684-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c8684-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8684-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8684-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8684-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8684-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8684-120">See also</span></span>

- [<span data-ttu-id="c8684-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="c8684-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
