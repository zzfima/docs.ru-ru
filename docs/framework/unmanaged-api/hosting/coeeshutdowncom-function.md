---
title: Функция CoEEShutDownCOM
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74548df512f68761b006e064a6db968e82b03813
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779120"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="338c7-102">Функция CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="338c7-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="338c7-103">Заставляет общеязыковой среды выполнения (CLR), чтобы освободить все указатели на интерфейс, содержащиеся внутри вызываемых оболочек времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="338c7-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="338c7-104">Это приводит к по освобождению всех кэшей вызываемой оболочки времени Выполнения.</span><span class="sxs-lookup"><span data-stu-id="338c7-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="338c7-105">Это глобальная функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="338c7-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="338c7-106">Вместо этого используйте точку входа для конкретной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="338c7-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="338c7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="338c7-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="338c7-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="338c7-108">Remarks</span></span>  
 <span data-ttu-id="338c7-109">`CoEEShutDownCOM` Функция сначала освобождает все оболочки RCW во всех контекстах и всех кэшах, а затем удаляет все уведомления демонтажа, существующие в программе установки.</span><span class="sxs-lookup"><span data-stu-id="338c7-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="338c7-110">Выгрузка DLL не выполнена.</span><span class="sxs-lookup"><span data-stu-id="338c7-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="338c7-111">Эта функция влияет на все среды выполнения, которые загружаются в процесс.</span><span class="sxs-lookup"><span data-stu-id="338c7-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="338c7-112">Начиная с .NET Framework 4, вызова точки входа для этой функции в конкретной среде выполнения, которые вы хотите повлиять на.</span><span class="sxs-lookup"><span data-stu-id="338c7-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="338c7-113">Чтобы получить точку входа, вызовите [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) метод и указать «CoEEShutDownCOM».</span><span class="sxs-lookup"><span data-stu-id="338c7-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="338c7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="338c7-114">Requirements</span></span>  
 <span data-ttu-id="338c7-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="338c7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="338c7-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="338c7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="338c7-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="338c7-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="338c7-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="338c7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338c7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="338c7-119">See also</span></span>

- [<span data-ttu-id="338c7-120">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="338c7-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
