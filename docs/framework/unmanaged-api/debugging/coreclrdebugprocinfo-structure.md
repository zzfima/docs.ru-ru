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
ms.openlocfilehash: 21fc34add4038d25d60e4728847e0d84914a14e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739427"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="b5288-102">Структура CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="b5288-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="b5288-103">Представляет процесс, который выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5288-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5288-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5288-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="b5288-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b5288-105">Members</span></span>  
  
|<span data-ttu-id="b5288-106">Член</span><span class="sxs-lookup"><span data-stu-id="b5288-106">Member</span></span>|<span data-ttu-id="b5288-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b5288-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="b5288-108">Идентификатор процесса, назначенный операционной системой.</span><span class="sxs-lookup"><span data-stu-id="b5288-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="b5288-109">Идентификатор процесса, назначенный прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="b5288-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="b5288-110">Этот идентификатор перезапускается реже, чем идентификатор ОС.</span><span class="sxs-lookup"><span data-stu-id="b5288-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="b5288-111">Командная строка процесса.</span><span class="sxs-lookup"><span data-stu-id="b5288-111">Command-line of the process.</span></span> <span data-ttu-id="b5288-112">Этот член может быть усечен.</span><span class="sxs-lookup"><span data-stu-id="b5288-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5288-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b5288-113">Requirements</span></span>  
 <span data-ttu-id="b5288-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5288-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5288-115">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="b5288-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b5288-116">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="b5288-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b5288-117">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b5288-117">**.NET Framework Versions:** 3.5 SP1</span></span>
