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
ms.openlocfilehash: 7d3c0d833208c91c548ea993bb6aa32e36e1f358
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776636"
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="54d43-102">Метод INotifyConnection2::RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="54d43-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="54d43-103">Устанавливает заданный источник уведомлений.</span><span class="sxs-lookup"><span data-stu-id="54d43-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d43-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54d43-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54d43-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="54d43-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="54d43-106">[in] Указывает объект для использования в качестве источника уведомлений.</span><span class="sxs-lookup"><span data-stu-id="54d43-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="54d43-107">[out] Получает объект для использования в качестве приемника уведомлений.</span><span class="sxs-lookup"><span data-stu-id="54d43-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54d43-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="54d43-108">Return Value</span></span>  
 <span data-ttu-id="54d43-109">Значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="54d43-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54d43-110">Требования</span><span class="sxs-lookup"><span data-stu-id="54d43-110">Requirements</span></span>  
 <span data-ttu-id="54d43-111">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="54d43-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d43-112">См. также</span><span class="sxs-lookup"><span data-stu-id="54d43-112">See also</span></span>

- [<span data-ttu-id="54d43-113">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="54d43-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="54d43-114">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="54d43-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="54d43-115">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="54d43-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="54d43-116">Метод UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="54d43-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
