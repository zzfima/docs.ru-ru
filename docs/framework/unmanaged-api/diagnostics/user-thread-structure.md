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
ms.openlocfilehash: 51db7a2b6464b562e09ce061991898a8d604ead1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437971"
---
# <a name="user_thread-structure"></a><span data-ttu-id="c1883-102">Структура USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="c1883-102">USER_THREAD Structure</span></span>
<span data-ttu-id="c1883-103">Предоставляет сведения отладчику о потоке.</span><span class="sxs-lookup"><span data-stu-id="c1883-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="c1883-104">Дополнительные сведения см. в описании метода [INotifySource2:: сетнотифифилтер](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c1883-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1883-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1883-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="c1883-106">Члены</span><span class="sxs-lookup"><span data-stu-id="c1883-106">Members</span></span>  
  
|<span data-ttu-id="c1883-107">Член</span><span class="sxs-lookup"><span data-stu-id="c1883-107">Member</span></span>|<span data-ttu-id="c1883-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c1883-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="c1883-109">Адрес буфера потока.</span><span class="sxs-lookup"><span data-stu-id="c1883-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="c1883-110">Длина буфера потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="c1883-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="c1883-111">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="c1883-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1883-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c1883-112">Requirements</span></span>  
 <span data-ttu-id="c1883-113">**Заголовок:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="c1883-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1883-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c1883-114">See also</span></span>

- [<span data-ttu-id="c1883-115">Метод SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="c1883-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="c1883-116">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="c1883-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
