---
title: "Метод INotifyConnection2::RegisterNotifySource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifyConnection2.RegisterNotifySource
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 370f19d9fd1cbc268d43b9970b0cf27290796562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="fb29d-102">Метод INotifyConnection2::RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="fb29d-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="fb29d-103">Устанавливает заданный источник уведомлений.</span><span class="sxs-lookup"><span data-stu-id="fb29d-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb29d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb29d-104">Syntax</span></span>  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb29d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb29d-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="fb29d-106">[in] Указывает объект для использования в качестве источника уведомления.</span><span class="sxs-lookup"><span data-stu-id="fb29d-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="fb29d-107">[out] Получает объект для использования в качестве приемника уведомлений.</span><span class="sxs-lookup"><span data-stu-id="fb29d-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb29d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fb29d-108">Return Value</span></span>  
 <span data-ttu-id="fb29d-109">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="fb29d-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb29d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="fb29d-110">Requirements</span></span>  
 <span data-ttu-id="fb29d-111">**Заголовок:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="fb29d-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb29d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fb29d-112">See Also</span></span>  
 [<span data-ttu-id="fb29d-113">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="fb29d-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="fb29d-114">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="fb29d-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="fb29d-115">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="fb29d-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="fb29d-116">Метод UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="fb29d-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
