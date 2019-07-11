---
title: Метод INotifySink2::OnSyncCallEnter
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5fc8b3e6432475468f1012313c95ddd2e22e026
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736260"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="fef44-102">Метод INotifySink2::OnSyncCallEnter</span><span class="sxs-lookup"><span data-stu-id="fef44-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="fef44-103">Вызывается при входе вызова.</span><span class="sxs-lookup"><span data-stu-id="fef44-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fef44-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fef44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fef44-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="fef44-106">[in] Идентификатор вызова, вводимым.</span><span class="sxs-lookup"><span data-stu-id="fef44-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="fef44-107">См. в разделе [структура CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="fef44-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="fef44-108">[in] Буфер для вызова.</span><span class="sxs-lookup"><span data-stu-id="fef44-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="fef44-109">[in] Размер буфера вызова в байтах.</span><span class="sxs-lookup"><span data-stu-id="fef44-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fef44-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fef44-110">Return Value</span></span>  
 <span data-ttu-id="fef44-111">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="fef44-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fef44-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fef44-112">Requirements</span></span>  
 <span data-ttu-id="fef44-113">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="fef44-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef44-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fef44-114">See also</span></span>

- [<span data-ttu-id="fef44-115">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="fef44-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="fef44-116">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="fef44-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="fef44-117">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="fef44-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
