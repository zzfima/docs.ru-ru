---
title: Структура CoreClrDebugRuntimeInfo
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b58832e110f67a54d3bd57a7284b2e26e43d6bf7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739402"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="713d1-102">Структура CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="713d1-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="713d1-103">Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="713d1-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="713d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="713d1-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="713d1-105">Участники</span><span class="sxs-lookup"><span data-stu-id="713d1-105">Members</span></span>  
  
|<span data-ttu-id="713d1-106">Член</span><span class="sxs-lookup"><span data-stu-id="713d1-106">Member</span></span>|<span data-ttu-id="713d1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="713d1-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="713d1-108">Идентификатор среды выполнения, назначаемый прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="713d1-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="713d1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="713d1-109">Requirements</span></span>  
 <span data-ttu-id="713d1-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="713d1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="713d1-111">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="713d1-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="713d1-112">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="713d1-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="713d1-113">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="713d1-113">**.NET Framework Versions:** 3.5 SP1</span></span>
