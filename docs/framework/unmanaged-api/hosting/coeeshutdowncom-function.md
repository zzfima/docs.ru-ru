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
ms.openlocfilehash: 4e85a9a98bf0550fa906f8b905c73890948f4ac1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124945"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="6cc12-102">Функция CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="6cc12-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="6cc12-103">Заставляет общеязыковую среду выполнения (CLR) освобождать все указатели интерфейсов, содержащиеся внутри вызываемых оболочек времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="6cc12-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="6cc12-104">Это приведет к освобождению всех кэшей RCW.</span><span class="sxs-lookup"><span data-stu-id="6cc12-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="6cc12-105">Эта глобальная функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6cc12-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="6cc12-106">Вместо этого используйте точку входа для конкретной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6cc12-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cc12-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cc12-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6cc12-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="6cc12-108">Remarks</span></span>  
 <span data-ttu-id="6cc12-109">Функция `CoEEShutDownCOM` сначала освобождает все вызываемые оболочки RCW во всех контекстах и во всех кэшах, а затем удаляет все уведомления о разрыве, существующие в программе установки.</span><span class="sxs-lookup"><span data-stu-id="6cc12-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="6cc12-110">Выгрузка библиотек DLL не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6cc12-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="6cc12-111">Эта функция влияет на все среды выполнения, загруженные в процесс.</span><span class="sxs-lookup"><span data-stu-id="6cc12-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="6cc12-112">Начиная с .NET Framework 4, вызовите точку входа для этой функции в конкретной среде выполнения, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="6cc12-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="6cc12-113">Чтобы получить точку входа, вызовите метод [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) и укажите "коишутдовнком".</span><span class="sxs-lookup"><span data-stu-id="6cc12-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cc12-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6cc12-114">Requirements</span></span>  
 <span data-ttu-id="6cc12-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cc12-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cc12-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6cc12-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6cc12-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6cc12-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6cc12-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cc12-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cc12-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6cc12-119">See also</span></span>

- [<span data-ttu-id="6cc12-120">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="6cc12-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
