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
ms.openlocfilehash: 8ddef35b1b707cc5c962402e880923dca7d4d9d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208154"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="0c09d-102">Функция CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="0c09d-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="0c09d-103">Заставляет общеязыковой среды выполнения (CLR), чтобы освободить все указатели на интерфейс, содержащиеся внутри вызываемых оболочек времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="0c09d-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="0c09d-104">Это приводит к по освобождению всех кэшей вызываемой оболочки времени Выполнения.</span><span class="sxs-lookup"><span data-stu-id="0c09d-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="0c09d-105">Это глобальная функция является устаревшей в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c09d-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="0c09d-106">Вместо этого используйте точку входа для конкретной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="0c09d-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c09d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c09d-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0c09d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c09d-108">Remarks</span></span>  
 <span data-ttu-id="0c09d-109">`CoEEShutDownCOM` Функция сначала освобождает все оболочки RCW во всех контекстах и всех кэшах, а затем удаляет все уведомления демонтажа, существующие в программе установки.</span><span class="sxs-lookup"><span data-stu-id="0c09d-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="0c09d-110">Выгрузка DLL не выполнена.</span><span class="sxs-lookup"><span data-stu-id="0c09d-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="0c09d-111">Эта функция влияет на все среды выполнения, которые загружаются в процесс.</span><span class="sxs-lookup"><span data-stu-id="0c09d-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="0c09d-112">Начиная с версии [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], вызова точки входа для этой функции в конкретной среде выполнения, необходимо провести эксперимент.</span><span class="sxs-lookup"><span data-stu-id="0c09d-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="0c09d-113">Чтобы получить точку входа, вызовите [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) метод и указать «CoEEShutDownCOM».</span><span class="sxs-lookup"><span data-stu-id="0c09d-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c09d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0c09d-114">Requirements</span></span>  
 <span data-ttu-id="0c09d-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c09d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c09d-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c09d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c09d-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c09d-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c09d-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c09d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c09d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0c09d-119">See also</span></span>

- [<span data-ttu-id="0c09d-120">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="0c09d-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
