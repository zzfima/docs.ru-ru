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
ms.openlocfilehash: d3e7f3208d7ac84645fa4c7ad7e0b71f6a0d3d3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429333"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="460c9-102">Функция CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="460c9-102">CorExitProcess Function</span></span>
<span data-ttu-id="460c9-103">Завершает работу текущего неуправляемого процесса.</span><span class="sxs-lookup"><span data-stu-id="460c9-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="460c9-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="460c9-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="460c9-105">Используйте [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="460c9-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460c9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="460c9-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="460c9-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="460c9-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="460c9-108">Целое число, определяющее код завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="460c9-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="460c9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="460c9-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="460c9-110">Начиная с версии [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` выходит из каждой запущенной среды выполнения в процесс, а не только привязан устаревшими интерфейсами API среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="460c9-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="460c9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="460c9-111">Requirements</span></span>  
 <span data-ttu-id="460c9-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="460c9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="460c9-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="460c9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="460c9-114">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="460c9-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="460c9-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="460c9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460c9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="460c9-116">See Also</span></span>  
 [<span data-ttu-id="460c9-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="460c9-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
