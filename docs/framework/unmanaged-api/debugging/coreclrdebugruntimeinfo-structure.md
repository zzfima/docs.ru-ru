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
ms.openlocfilehash: 88fcc5959054f1cdf7c9543674584a4bde26d896
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966046"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="d8c6d-102">Структура CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="d8c6d-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="d8c6d-103">Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d8c6d-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8c6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8c6d-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="d8c6d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d8c6d-105">Members</span></span>  
  
|<span data-ttu-id="d8c6d-106">Член</span><span class="sxs-lookup"><span data-stu-id="d8c6d-106">Member</span></span>|<span data-ttu-id="d8c6d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d8c6d-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="d8c6d-108">Идентификатор среды выполнения, назначаемый прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="d8c6d-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8c6d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d8c6d-109">Requirements</span></span>  
 <span data-ttu-id="d8c6d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8c6d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8c6d-111">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="d8c6d-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d8c6d-112">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d8c6d-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d8c6d-113">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="d8c6d-113">**.NET Framework Versions:** 3.5 SP1</span></span>
