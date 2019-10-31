---
title: Метод ICorConfiguration::AddDebuggerSpecialThread
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
ms.openlocfilehash: c5d6cfa3826667514eb70f9bb0df118d9ba0d07c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127821"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="f596c-102">Метод ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="f596c-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="f596c-103">Указывает службам отладки, что определенному потоку должен быть разрешено продолжать выполнение, пока отладчик не остановит работу приложения во время управляемых или неуправляемых сценариев отладки.</span><span class="sxs-lookup"><span data-stu-id="f596c-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f596c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f596c-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f596c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f596c-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="f596c-106">окне Идентификатор потока, который должен быть разрешен для продолжения выполнения.</span><span class="sxs-lookup"><span data-stu-id="f596c-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f596c-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="f596c-107">Remarks</span></span>  
 <span data-ttu-id="f596c-108">Указанный поток не может выполнять управляемый код или вводить среду выполнения каким бы то ни было образом.</span><span class="sxs-lookup"><span data-stu-id="f596c-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="f596c-109">Примером такого потока может быть внутрипроцессный поток для поддержки устаревших отладчиков скриптов.</span><span class="sxs-lookup"><span data-stu-id="f596c-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f596c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f596c-110">Requirements</span></span>  
 <span data-ttu-id="f596c-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f596c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f596c-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f596c-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f596c-113">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f596c-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f596c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f596c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f596c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f596c-115">See also</span></span>

- [<span data-ttu-id="f596c-116">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f596c-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
