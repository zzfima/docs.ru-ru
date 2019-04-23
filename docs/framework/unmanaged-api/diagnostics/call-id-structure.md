---
title: Структура CALL_ID
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6fa729b131d12b2825a2def700fd918ce8acc40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220179"
---
# <a name="callid-structure"></a><span data-ttu-id="cd7e9-102">Структура CALL_ID</span><span class="sxs-lookup"><span data-stu-id="cd7e9-102">CALL_ID Structure</span></span>
<span data-ttu-id="cd7e9-103">Сведения о функции, которая вызывается отладчиком.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="cd7e9-104">См. в разделе [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) интерфейс Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7e9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd7e9-105">Syntax</span></span>  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="cd7e9-106">Участники</span><span class="sxs-lookup"><span data-stu-id="cd7e9-106">Members</span></span>  
  
|<span data-ttu-id="cd7e9-107">Член</span><span class="sxs-lookup"><span data-stu-id="cd7e9-107">Member</span></span>|<span data-ttu-id="cd7e9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="cd7e9-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="cd7e9-109">Определяет, выполняет вызов машину.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="cd7e9-110">Определяет процессор компьютера.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="cd7e9-111">Определяет поток, который выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="cd7e9-112">Указывает адрес стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="cd7e9-113">Указывает адрес вызова.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="cd7e9-114">Определяет, будет исполнен в машину.</span><span class="sxs-lookup"><span data-stu-id="cd7e9-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd7e9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="cd7e9-115">Requirements</span></span>  
 <span data-ttu-id="cd7e9-116">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="cd7e9-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7e9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cd7e9-117">See also</span></span>

- [<span data-ttu-id="cd7e9-118">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="cd7e9-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="cd7e9-119">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="cd7e9-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
