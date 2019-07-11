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
ms.openlocfilehash: 2823c018ff22607052cb9a298f69dbd0c4fe2c23
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769501"
---
# <a name="callid-structure"></a><span data-ttu-id="89bcb-102">Структура CALL_ID</span><span class="sxs-lookup"><span data-stu-id="89bcb-102">CALL_ID Structure</span></span>
<span data-ttu-id="89bcb-103">Сведения о функции, которая вызывается отладчиком.</span><span class="sxs-lookup"><span data-stu-id="89bcb-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="89bcb-104">См. в разделе [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) интерфейс Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="89bcb-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89bcb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89bcb-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="89bcb-106">Участники</span><span class="sxs-lookup"><span data-stu-id="89bcb-106">Members</span></span>  
  
|<span data-ttu-id="89bcb-107">Член</span><span class="sxs-lookup"><span data-stu-id="89bcb-107">Member</span></span>|<span data-ttu-id="89bcb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="89bcb-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="89bcb-109">Определяет, выполняет вызов машину.</span><span class="sxs-lookup"><span data-stu-id="89bcb-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="89bcb-110">Определяет процессор компьютера.</span><span class="sxs-lookup"><span data-stu-id="89bcb-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="89bcb-111">Определяет поток, который выполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="89bcb-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="89bcb-112">Указывает адрес стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="89bcb-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="89bcb-113">Указывает адрес вызова.</span><span class="sxs-lookup"><span data-stu-id="89bcb-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="89bcb-114">Определяет, будет исполнен в машину.</span><span class="sxs-lookup"><span data-stu-id="89bcb-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89bcb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="89bcb-115">Requirements</span></span>  
 <span data-ttu-id="89bcb-116">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="89bcb-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89bcb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="89bcb-117">See also</span></span>

- [<span data-ttu-id="89bcb-118">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="89bcb-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="89bcb-119">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="89bcb-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
