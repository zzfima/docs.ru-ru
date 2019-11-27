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
ms.openlocfilehash: 8c606f67766334800444f39b115d90f65ecca13d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448594"
---
# <a name="call_id-structure"></a><span data-ttu-id="ee0a3-102">Структура CALL_ID</span><span class="sxs-lookup"><span data-stu-id="ee0a3-102">CALL_ID Structure</span></span>
<span data-ttu-id="ee0a3-103">Предоставляет сведения отладчику о вызываемой функции.</span><span class="sxs-lookup"><span data-stu-id="ee0a3-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="ee0a3-104">Дополнительные сведения см. в интерфейсе [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ee0a3-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0a3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee0a3-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ee0a3-106">Члены</span><span class="sxs-lookup"><span data-stu-id="ee0a3-106">Members</span></span>  
  
|<span data-ttu-id="ee0a3-107">Член</span><span class="sxs-lookup"><span data-stu-id="ee0a3-107">Member</span></span>|<span data-ttu-id="ee0a3-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ee0a3-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="ee0a3-109">Идентифицирует компьютер, выполняющий вызов.</span><span class="sxs-lookup"><span data-stu-id="ee0a3-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="ee0a3-110">Идентифицирует процессор компьютера.</span><span class="sxs-lookup"><span data-stu-id="ee0a3-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="ee0a3-111">Идентифицирует поток, который исполняет вызов.</span><span class="sxs-lookup"><span data-stu-id="ee0a3-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="ee0a3-112">Задает адрес стека вызовов.</span><span class="sxs-lookup"><span data-stu-id="ee0a3-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="ee0a3-113">Задает адрес вызова.</span><span class="sxs-lookup"><span data-stu-id="ee0a3-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="ee0a3-114">Определяет компьютер, который будет выполнять вызов.</span><span class="sxs-lookup"><span data-stu-id="ee0a3-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee0a3-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ee0a3-115">Requirements</span></span>  
 <span data-ttu-id="ee0a3-116">**Заголовок:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="ee0a3-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0a3-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="ee0a3-117">See also</span></span>

- [<span data-ttu-id="ee0a3-118">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="ee0a3-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="ee0a3-119">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ee0a3-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
