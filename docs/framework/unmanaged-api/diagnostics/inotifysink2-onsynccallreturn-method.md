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
ms.openlocfilehash: 84fd40dbecf9a866a4ec0889cbb62c475c063475
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736219"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="e3256-102">Метод INotifySink2::OnSyncCallReturn</span><span class="sxs-lookup"><span data-stu-id="e3256-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="e3256-103">Вызывается при возврате вызова.</span><span class="sxs-lookup"><span data-stu-id="e3256-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3256-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3256-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3256-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3256-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="e3256-106">[in] Идентификатор, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="e3256-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="e3256-107">См. в разделе [структура CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="e3256-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="e3256-108">[in] Буфер для вызова.</span><span class="sxs-lookup"><span data-stu-id="e3256-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="e3256-109">[in] Размер буфера вызова в байтах.</span><span class="sxs-lookup"><span data-stu-id="e3256-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3256-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3256-110">Return Value</span></span>  
 <span data-ttu-id="e3256-111">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e3256-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3256-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e3256-112">Requirements</span></span>  
 <span data-ttu-id="e3256-113">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="e3256-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3256-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e3256-114">See also</span></span>

- [<span data-ttu-id="e3256-115">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="e3256-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="e3256-116">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="e3256-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="e3256-117">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="e3256-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
