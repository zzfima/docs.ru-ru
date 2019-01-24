---
title: Метод INotifyConnection2::RegisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5895dc3cb64b72380dead1e048c012b586c4f48e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550725"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="e3a83-102">Метод INotifyConnection2::RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="e3a83-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="e3a83-103">Устанавливает заданный источник уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e3a83-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a83-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3a83-104">Syntax</span></span>  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3a83-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3a83-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="e3a83-106">[in] Указывает объект для использования в качестве источника уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e3a83-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="e3a83-107">[out] Получает объект для использования в качестве приемника уведомлений.</span><span class="sxs-lookup"><span data-stu-id="e3a83-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3a83-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3a83-108">Return Value</span></span>  
 <span data-ttu-id="e3a83-109">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e3a83-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3a83-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e3a83-110">Requirements</span></span>  
 <span data-ttu-id="e3a83-111">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="e3a83-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a83-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e3a83-112">See also</span></span>
- [<span data-ttu-id="e3a83-113">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="e3a83-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="e3a83-114">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="e3a83-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="e3a83-115">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="e3a83-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="e3a83-116">Метод UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="e3a83-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
