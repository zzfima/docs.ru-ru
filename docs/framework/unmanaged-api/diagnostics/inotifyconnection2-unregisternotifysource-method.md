---
title: Метод INotifyConnection2::UnregisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4b4f90f918c872f3227ac22f4cccadcbf3194a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="072f4-102">Метод INotifyConnection2::UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="072f4-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="072f4-103">Удаляет заданный объект источника уведомлений из соединения.</span><span class="sxs-lookup"><span data-stu-id="072f4-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="072f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="072f4-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="072f4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="072f4-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="072f4-106">[in] Объект уведомления для отмены регистрации.</span><span class="sxs-lookup"><span data-stu-id="072f4-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="072f4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="072f4-107">Return Value</span></span>  
 <span data-ttu-id="072f4-108">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="072f4-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="072f4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="072f4-109">Requirements</span></span>  
 <span data-ttu-id="072f4-110">**Заголовок:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="072f4-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072f4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="072f4-111">See Also</span></span>  
 [<span data-ttu-id="072f4-112">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="072f4-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="072f4-113">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="072f4-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="072f4-114">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="072f4-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="072f4-115">Метод RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="072f4-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
