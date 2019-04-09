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
ms.openlocfilehash: 0adc6ec1db3f12d1850bb6ff9a01d5b6cc5f90c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157928"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="3a7d0-102">Метод INotifySink2::OnSyncCallReturn</span><span class="sxs-lookup"><span data-stu-id="3a7d0-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="3a7d0-103">Вызывается при возврате вызова.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a7d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a7d0-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a7d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a7d0-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="3a7d0-106">[in] Идентификатор, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="3a7d0-107">См. в разделе [структура CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="3a7d0-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="3a7d0-108">[in] Буфер для вызова.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="3a7d0-109">[in] Размер буфера вызова в байтах.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a7d0-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3a7d0-110">Return Value</span></span>  
 <span data-ttu-id="3a7d0-111">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a7d0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3a7d0-112">Requirements</span></span>  
 <span data-ttu-id="3a7d0-113">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="3a7d0-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a7d0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3a7d0-114">See also</span></span>

- [<span data-ttu-id="3a7d0-115">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="3a7d0-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="3a7d0-116">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="3a7d0-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="3a7d0-117">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="3a7d0-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
