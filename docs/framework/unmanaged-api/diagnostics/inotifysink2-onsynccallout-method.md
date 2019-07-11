---
title: Метод INotifySink2::OnSyncCallOut
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4cea67587e4a33b4b9f8cbaa23cb7d299004a46
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736160"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="0484b-102">Метод INotifySink2::OnSyncCallOut</span><span class="sxs-lookup"><span data-stu-id="0484b-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="0484b-103">Вызывается, когда вызова.</span><span class="sxs-lookup"><span data-stu-id="0484b-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0484b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0484b-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0484b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0484b-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="0484b-106">[in] Идентификатор вызова, который вышел. См. в разделе [структура CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="0484b-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="0484b-107">[out] Буфер для вызова.</span><span class="sxs-lookup"><span data-stu-id="0484b-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="0484b-108">[out] Размер буфера вызова в байтах.</span><span class="sxs-lookup"><span data-stu-id="0484b-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0484b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0484b-109">Return Value</span></span>  
 <span data-ttu-id="0484b-110">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="0484b-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0484b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0484b-111">Requirements</span></span>  
 <span data-ttu-id="0484b-112">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="0484b-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0484b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0484b-113">See also</span></span>

- [<span data-ttu-id="0484b-114">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="0484b-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="0484b-115">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="0484b-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="0484b-116">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="0484b-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
