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
ms.openlocfilehash: e12882e53d1aa2120ab5c4b6793d7f2e34be76eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132163"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="424bb-102">Структура CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="424bb-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="424bb-103">Представляет процесс, который выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="424bb-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="424bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="424bb-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="424bb-105">Члены</span><span class="sxs-lookup"><span data-stu-id="424bb-105">Members</span></span>  
  
|<span data-ttu-id="424bb-106">Член</span><span class="sxs-lookup"><span data-stu-id="424bb-106">Member</span></span>|<span data-ttu-id="424bb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="424bb-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="424bb-108">Идентификатор процесса, назначенный операционной системой.</span><span class="sxs-lookup"><span data-stu-id="424bb-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="424bb-109">Идентификатор процесса, назначенный прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="424bb-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="424bb-110">Этот идентификатор перезапускается реже, чем идентификатор ОС.</span><span class="sxs-lookup"><span data-stu-id="424bb-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="424bb-111">Командная строка процесса.</span><span class="sxs-lookup"><span data-stu-id="424bb-111">Command-line of the process.</span></span> <span data-ttu-id="424bb-112">Этот член может быть усечен.</span><span class="sxs-lookup"><span data-stu-id="424bb-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="424bb-113">Требования</span><span class="sxs-lookup"><span data-stu-id="424bb-113">Requirements</span></span>  
 <span data-ttu-id="424bb-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="424bb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="424bb-115">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="424bb-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="424bb-116">**Библиотека:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="424bb-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="424bb-117">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="424bb-117">**.NET Framework Versions:** 3.5 SP1</span></span>
