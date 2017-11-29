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
ms.openlocfilehash: c44db9021a7dbf5b497db3536eddcea020e71bf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="callid-structure"></a><span data-ttu-id="ca019-102">Структура CALL_ID</span><span class="sxs-lookup"><span data-stu-id="ca019-102">CALL_ID Structure</span></span>
<span data-ttu-id="ca019-103">Сведения о функции, которая вызывается в отладчике.</span><span class="sxs-lookup"><span data-stu-id="ca019-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="ca019-104">В разделе [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) интерфейс для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="ca019-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca019-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca019-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ca019-106">Члены</span><span class="sxs-lookup"><span data-stu-id="ca019-106">Members</span></span>  
  
|<span data-ttu-id="ca019-107">Член</span><span class="sxs-lookup"><span data-stu-id="ca019-107">Member</span></span>|<span data-ttu-id="ca019-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ca019-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="ca019-109">Идентифицирует компьютер, который выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="ca019-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="ca019-110">Определяет процессор компьютера.</span><span class="sxs-lookup"><span data-stu-id="ca019-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="ca019-111">Определяет поток, который выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="ca019-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="ca019-112">Задает адрес стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="ca019-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="ca019-113">Задает адрес вызова.</span><span class="sxs-lookup"><span data-stu-id="ca019-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="ca019-114">Идентифицирует компьютер, который будет выполнять вызов.</span><span class="sxs-lookup"><span data-stu-id="ca019-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca019-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ca019-115">Requirements</span></span>  
 <span data-ttu-id="ca019-116">**Заголовок:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="ca019-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca019-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ca019-117">See Also</span></span>  
 [<span data-ttu-id="ca019-118">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="ca019-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="ca019-119">Структуры хранения символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ca019-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
