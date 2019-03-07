---
title: Метод INotifySink2::OnSyncCallReturn
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae3067e6941451d4debd8d18ca58a91708a48e56
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487261"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="5ba77-102">Метод INotifySink2::OnSyncCallReturn</span><span class="sxs-lookup"><span data-stu-id="5ba77-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="5ba77-103">Вызывается при возврате вызова.</span><span class="sxs-lookup"><span data-stu-id="5ba77-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ba77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ba77-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ba77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ba77-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="5ba77-106">[in] Идентификатор, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="5ba77-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="5ba77-107">См. в разделе [структура CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="5ba77-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="5ba77-108">[in] Буфер для вызова.</span><span class="sxs-lookup"><span data-stu-id="5ba77-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="5ba77-109">[in] Размер буфера вызова в байтах.</span><span class="sxs-lookup"><span data-stu-id="5ba77-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ba77-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5ba77-110">Return Value</span></span>  
 <span data-ttu-id="5ba77-111">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5ba77-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ba77-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5ba77-112">Requirements</span></span>  
 <span data-ttu-id="5ba77-113">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="5ba77-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ba77-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5ba77-114">See also</span></span>
- [<span data-ttu-id="5ba77-115">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="5ba77-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="5ba77-116">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="5ba77-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="5ba77-117">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="5ba77-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
