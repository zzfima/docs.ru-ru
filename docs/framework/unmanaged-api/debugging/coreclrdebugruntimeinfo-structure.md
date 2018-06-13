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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402074"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="46136-102">Структура CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="46136-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="46136-103">Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="46136-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46136-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46136-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="46136-105">Участники</span><span class="sxs-lookup"><span data-stu-id="46136-105">Members</span></span>  
  
|<span data-ttu-id="46136-106">Член</span><span class="sxs-lookup"><span data-stu-id="46136-106">Member</span></span>|<span data-ttu-id="46136-107">Описание</span><span class="sxs-lookup"><span data-stu-id="46136-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="46136-108">Идентификатор среды выполнения, назначаемый прокси-сервером удаленной отладки, работающим на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="46136-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="46136-109">Требования</span><span class="sxs-lookup"><span data-stu-id="46136-109">Requirements</span></span>  
 <span data-ttu-id="46136-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46136-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46136-111">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="46136-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="46136-112">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="46136-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="46136-113">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="46136-113">**.NET Framework Versions:** 3.5 SP1</span></span>
