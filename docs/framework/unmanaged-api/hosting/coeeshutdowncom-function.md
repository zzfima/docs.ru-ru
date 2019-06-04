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
ms.openlocfilehash: 0d2b82bc056acd2e620461081b5f8c9d45fc152c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490643"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="738e8-102">Функция CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="738e8-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="738e8-103">Заставляет общеязыковой среды выполнения (CLR), чтобы освободить все указатели на интерфейс, содержащиеся внутри вызываемых оболочек времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="738e8-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="738e8-104">Это приводит к по освобождению всех кэшей вызываемой оболочки времени Выполнения.</span><span class="sxs-lookup"><span data-stu-id="738e8-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="738e8-105">Это глобальная функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="738e8-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="738e8-106">Вместо этого используйте точку входа для конкретной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="738e8-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="738e8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="738e8-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="738e8-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="738e8-108">Remarks</span></span>  
 <span data-ttu-id="738e8-109">`CoEEShutDownCOM` Функция сначала освобождает все оболочки RCW во всех контекстах и всех кэшах, а затем удаляет все уведомления демонтажа, существующие в программе установки.</span><span class="sxs-lookup"><span data-stu-id="738e8-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="738e8-110">Выгрузка DLL не выполнена.</span><span class="sxs-lookup"><span data-stu-id="738e8-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="738e8-111">Эта функция влияет на все среды выполнения, которые загружаются в процесс.</span><span class="sxs-lookup"><span data-stu-id="738e8-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="738e8-112">Начиная с .NET Framework 4, вызова точки входа для этой функции в конкретной среде выполнения, которые вы хотите повлиять на.</span><span class="sxs-lookup"><span data-stu-id="738e8-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="738e8-113">Чтобы получить точку входа, вызовите [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) метод и указать «CoEEShutDownCOM».</span><span class="sxs-lookup"><span data-stu-id="738e8-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="738e8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="738e8-114">Requirements</span></span>  
 <span data-ttu-id="738e8-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="738e8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="738e8-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="738e8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="738e8-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="738e8-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="738e8-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="738e8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738e8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="738e8-119">See also</span></span>

- [<span data-ttu-id="738e8-120">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="738e8-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
