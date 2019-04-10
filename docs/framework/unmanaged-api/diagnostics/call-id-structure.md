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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220179"
---
# <a name="callid-structure"></a><span data-ttu-id="72263-102">Структура CALL_ID</span><span class="sxs-lookup"><span data-stu-id="72263-102">CALL_ID Structure</span></span>
<span data-ttu-id="72263-103">Сведения о функции, которая вызывается отладчиком.</span><span class="sxs-lookup"><span data-stu-id="72263-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="72263-104">См. в разделе [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) интерфейс Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="72263-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72263-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72263-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="72263-106">Участники</span><span class="sxs-lookup"><span data-stu-id="72263-106">Members</span></span>  
  
|<span data-ttu-id="72263-107">Член</span><span class="sxs-lookup"><span data-stu-id="72263-107">Member</span></span>|<span data-ttu-id="72263-108">Описание</span><span class="sxs-lookup"><span data-stu-id="72263-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="72263-109">Определяет, выполняет вызов машину.</span><span class="sxs-lookup"><span data-stu-id="72263-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="72263-110">Определяет процессор компьютера.</span><span class="sxs-lookup"><span data-stu-id="72263-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="72263-111">Определяет поток, который выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="72263-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="72263-112">Указывает адрес стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="72263-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="72263-113">Указывает адрес вызова.</span><span class="sxs-lookup"><span data-stu-id="72263-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="72263-114">Определяет, будет исполнен в машину.</span><span class="sxs-lookup"><span data-stu-id="72263-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72263-115">Требования</span><span class="sxs-lookup"><span data-stu-id="72263-115">Requirements</span></span>  
 <span data-ttu-id="72263-116">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="72263-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72263-117">См. также</span><span class="sxs-lookup"><span data-stu-id="72263-117">See also</span></span>

- [<span data-ttu-id="72263-118">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="72263-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="72263-119">Структуры хранения символов диагностики</span><span class="sxs-lookup"><span data-stu-id="72263-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
