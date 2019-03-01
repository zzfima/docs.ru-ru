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
ms.openlocfilehash: 5e0afe278b22e54b326ef17dc416b4632a853eda
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212343"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="c7ed0-102">Функция CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="c7ed0-102">CorExitProcess Function</span></span>
<span data-ttu-id="c7ed0-103">Завершает работу текущего неуправляемого процесса.</span><span class="sxs-lookup"><span data-stu-id="c7ed0-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="c7ed0-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7ed0-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c7ed0-105">Используйте [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="c7ed0-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ed0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7ed0-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7ed0-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7ed0-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="c7ed0-108">Целое число, определяющее код завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="c7ed0-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7ed0-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7ed0-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7ed0-110">Начиная с версии [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` выходит из каждой запущенной среды выполнения в процессе, а не только среды выполнения, к которому привязан интерфейсов API прежних версий.</span><span class="sxs-lookup"><span data-stu-id="c7ed0-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ed0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c7ed0-111">Requirements</span></span>  
 <span data-ttu-id="c7ed0-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ed0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ed0-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7ed0-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7ed0-114">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7ed0-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7ed0-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ed0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ed0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c7ed0-116">See also</span></span>
- [<span data-ttu-id="c7ed0-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c7ed0-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
