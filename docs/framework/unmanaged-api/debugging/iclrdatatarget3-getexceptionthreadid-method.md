---
title: Метод ICLRDataTarget3::GetExceptionThreadID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
ms.openlocfilehash: 5e7fd2f277a9c3d8410020a53d348456ef9deffb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111904"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="dfb26-102">Метод ICLRDataTarget3::GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="dfb26-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="dfb26-103">Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="dfb26-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfb26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfb26-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfb26-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="dfb26-106">[из] Идентификатор потока, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="dfb26-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfb26-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dfb26-107">Return Value</span></span>  
 <span data-ttu-id="dfb26-108">Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое.</span><span class="sxs-lookup"><span data-stu-id="dfb26-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="dfb26-109">Коды `HRESULT` могут включать значения, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="dfb26-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="dfb26-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="dfb26-110">Return code</span></span>|<span data-ttu-id="dfb26-111">Описание</span><span class="sxs-lookup"><span data-stu-id="dfb26-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="dfb26-112">Метод успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="dfb26-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="dfb26-113">Не удалось найти допустимый идентификатор потока для исключения.</span><span class="sxs-lookup"><span data-stu-id="dfb26-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfb26-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="dfb26-114">Remarks</span></span>  
 <span data-ttu-id="dfb26-115">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="dfb26-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb26-116">Требования</span><span class="sxs-lookup"><span data-stu-id="dfb26-116">Requirements</span></span>  
 <span data-ttu-id="dfb26-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb26-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb26-118">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="dfb26-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dfb26-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfb26-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfb26-120">**Версии платформы .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb26-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb26-121">См. также</span><span class="sxs-lookup"><span data-stu-id="dfb26-121">See also</span></span>

- [<span data-ttu-id="dfb26-122">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="dfb26-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="dfb26-123">Метод GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="dfb26-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="dfb26-124">Метод GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="dfb26-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
