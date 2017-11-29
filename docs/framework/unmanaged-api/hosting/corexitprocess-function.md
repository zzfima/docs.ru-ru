---
title: "Функция CorExitProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CorExitProcess
helpviewer_keywords: CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75b35631bad5de46d48ed818c6f929f25a5f7e66
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corexitprocess-function"></a><span data-ttu-id="4b32b-102">Функция CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="4b32b-102">CorExitProcess Function</span></span>
<span data-ttu-id="4b32b-103">Завершает работу текущего неуправляемого процесса.</span><span class="sxs-lookup"><span data-stu-id="4b32b-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="4b32b-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b32b-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="4b32b-105">Используйте [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="4b32b-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b32b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b32b-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b32b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b32b-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="4b32b-108">Целое число, определяющее код завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="4b32b-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b32b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b32b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b32b-110">Начиная с версии [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` выходит из каждой запущенной среды выполнения в процесс, а не только привязан устаревшими интерфейсами API среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b32b-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b32b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4b32b-111">Requirements</span></span>  
 <span data-ttu-id="4b32b-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b32b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b32b-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b32b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b32b-114">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b32b-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b32b-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b32b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b32b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4b32b-116">See Also</span></span>  
 [<span data-ttu-id="4b32b-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="4b32b-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
