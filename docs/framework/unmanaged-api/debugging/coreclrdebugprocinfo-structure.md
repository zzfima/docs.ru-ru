---
title: "Структура CoreClrDebugProcInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugProcInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d341b875f9f64b9aa1fcdcf21668dafea0beac12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="b0ed4-102">Структура CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="b0ed4-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="b0ed4-103">Представляет процесс, который выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0ed4-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ed4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0ed4-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="b0ed4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b0ed4-105">Members</span></span>  
  
|<span data-ttu-id="b0ed4-106">Член</span><span class="sxs-lookup"><span data-stu-id="b0ed4-106">Member</span></span>|<span data-ttu-id="b0ed4-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b0ed4-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="b0ed4-108">Идентификатор процесса, назначенный операционной системой.</span><span class="sxs-lookup"><span data-stu-id="b0ed4-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="b0ed4-109">Идентификатор процесса, назначенный прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0ed4-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="b0ed4-110">Этот идентификатор перезапускается реже, чем идентификатор ОС.</span><span class="sxs-lookup"><span data-stu-id="b0ed4-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="b0ed4-111">Командная строка процесса.</span><span class="sxs-lookup"><span data-stu-id="b0ed4-111">Command-line of the process.</span></span> <span data-ttu-id="b0ed4-112">Этот член может быть усечен.</span><span class="sxs-lookup"><span data-stu-id="b0ed4-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0ed4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b0ed4-113">Requirements</span></span>  
 <span data-ttu-id="b0ed4-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0ed4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0ed4-115">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="b0ed4-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b0ed4-116">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="b0ed4-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b0ed4-117">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b0ed4-117">**.NET Framework Versions:** 3.5 SP1</span></span>
