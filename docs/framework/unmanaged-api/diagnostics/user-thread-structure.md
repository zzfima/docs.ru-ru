---
title: Структура USER_THREAD
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11551221732e454e48111d48d60ca9b72f7f9b66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127169"
---
# <a name="userthread-structure"></a><span data-ttu-id="b29d8-102">Структура USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="b29d8-102">USER_THREAD Structure</span></span>
<span data-ttu-id="b29d8-103">Предоставляет сведения о потоке отладчику.</span><span class="sxs-lookup"><span data-stu-id="b29d8-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="b29d8-104">Дополнительные сведения см. в разделе [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="b29d8-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b29d8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b29d8-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="b29d8-106">Участники</span><span class="sxs-lookup"><span data-stu-id="b29d8-106">Members</span></span>  
  
|<span data-ttu-id="b29d8-107">Член</span><span class="sxs-lookup"><span data-stu-id="b29d8-107">Member</span></span>|<span data-ttu-id="b29d8-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b29d8-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="b29d8-109">Адрес буфера потока.</span><span class="sxs-lookup"><span data-stu-id="b29d8-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="b29d8-110">Длина буфера потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="b29d8-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="b29d8-111">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="b29d8-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b29d8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b29d8-112">Requirements</span></span>  
 <span data-ttu-id="b29d8-113">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="b29d8-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29d8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b29d8-114">See also</span></span>

- [<span data-ttu-id="b29d8-115">Метод SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="b29d8-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="b29d8-116">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="b29d8-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
