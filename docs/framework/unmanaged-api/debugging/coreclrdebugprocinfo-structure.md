---
title: Структура CoreClrDebugProcInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9d4b27ca0bf454b42f15b849008e5a3019bb09a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864082"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="114aa-102">Структура CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="114aa-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="114aa-103">Представляет процесс, который выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="114aa-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="114aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="114aa-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="114aa-105">Участники</span><span class="sxs-lookup"><span data-stu-id="114aa-105">Members</span></span>  
  
|<span data-ttu-id="114aa-106">Член</span><span class="sxs-lookup"><span data-stu-id="114aa-106">Member</span></span>|<span data-ttu-id="114aa-107">Описание</span><span class="sxs-lookup"><span data-stu-id="114aa-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="114aa-108">Идентификатор процесса, назначенный операционной системой.</span><span class="sxs-lookup"><span data-stu-id="114aa-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="114aa-109">Идентификатор процесса, назначенный прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="114aa-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="114aa-110">Этот идентификатор перезапускается реже, чем идентификатор ОС.</span><span class="sxs-lookup"><span data-stu-id="114aa-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="114aa-111">Командная строка процесса.</span><span class="sxs-lookup"><span data-stu-id="114aa-111">Command-line of the process.</span></span> <span data-ttu-id="114aa-112">Этот член может быть усечен.</span><span class="sxs-lookup"><span data-stu-id="114aa-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="114aa-113">Требования</span><span class="sxs-lookup"><span data-stu-id="114aa-113">Requirements</span></span>  
 <span data-ttu-id="114aa-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="114aa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="114aa-115">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="114aa-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="114aa-116">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="114aa-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="114aa-117">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="114aa-117">**.NET Framework Versions:** 3.5 SP1</span></span>
