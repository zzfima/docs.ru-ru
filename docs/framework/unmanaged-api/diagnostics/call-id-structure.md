---
title: "Структура CALL_ID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CALL_ID
api_location: diasymreader.dll
api_type: COM
f1_keywords: CALL_ID
helpviewer_keywords: CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71fd69cbcced1440839b9eedf8fbe3d8f5b90646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="callid-structure"></a><span data-ttu-id="f3741-102">Структура CALL_ID</span><span class="sxs-lookup"><span data-stu-id="f3741-102">CALL_ID Structure</span></span>
<span data-ttu-id="f3741-103">Сведения о функции, которая вызывается в отладчике.</span><span class="sxs-lookup"><span data-stu-id="f3741-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="f3741-104">В разделе [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) интерфейс для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="f3741-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3741-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3741-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f3741-106">Участники</span><span class="sxs-lookup"><span data-stu-id="f3741-106">Members</span></span>  
  
|<span data-ttu-id="f3741-107">Член</span><span class="sxs-lookup"><span data-stu-id="f3741-107">Member</span></span>|<span data-ttu-id="f3741-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="f3741-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="f3741-109">Идентифицирует компьютер, который выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="f3741-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="f3741-110">Определяет процессор компьютера.</span><span class="sxs-lookup"><span data-stu-id="f3741-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="f3741-111">Определяет поток, который выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="f3741-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="f3741-112">Задает адрес стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="f3741-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="f3741-113">Задает адрес вызова.</span><span class="sxs-lookup"><span data-stu-id="f3741-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="f3741-114">Идентифицирует компьютер, который будет выполнять вызов.</span><span class="sxs-lookup"><span data-stu-id="f3741-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3741-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f3741-115">Requirements</span></span>  
 <span data-ttu-id="f3741-116">**Заголовок:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="f3741-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3741-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f3741-117">See Also</span></span>  
 [<span data-ttu-id="f3741-118">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="f3741-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="f3741-119">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f3741-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
