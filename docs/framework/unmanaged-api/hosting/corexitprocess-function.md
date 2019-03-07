---
title: Функция CorExitProcess
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a93e73fa8345b48e604d6f63d16170d850ead451
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484580"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="0b477-102">Функция CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="0b477-102">CorExitProcess Function</span></span>
<span data-ttu-id="0b477-103">Завершает работу текущего неуправляемого процесса.</span><span class="sxs-lookup"><span data-stu-id="0b477-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="0b477-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b477-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="0b477-105">Используйте [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="0b477-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b477-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b477-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b477-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b477-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="0b477-108">Целое число, определяющее код завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="0b477-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b477-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b477-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b477-110">Начиная с версии [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` выходит из каждой запущенной среды выполнения в процессе, а не только среды выполнения, к которому привязан интерфейсов API прежних версий.</span><span class="sxs-lookup"><span data-stu-id="0b477-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b477-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0b477-111">Requirements</span></span>  
 <span data-ttu-id="0b477-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b477-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b477-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b477-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b477-114">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b477-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b477-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b477-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b477-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0b477-116">See also</span></span>
- [<span data-ttu-id="0b477-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="0b477-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
