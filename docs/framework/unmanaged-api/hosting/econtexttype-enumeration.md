---
title: Перечисление EContextType
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3643bf4880532a46fe7f9f57b8077032013728
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796043"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="2eba8-102">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="2eba8-102">EContextType Enumeration</span></span>
<span data-ttu-id="2eba8-103">Описывает контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="2eba8-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eba8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2eba8-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="2eba8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2eba8-105">Members</span></span>  
  
|<span data-ttu-id="2eba8-106">Член</span><span class="sxs-lookup"><span data-stu-id="2eba8-106">Member</span></span>|<span data-ttu-id="2eba8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2eba8-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="2eba8-108">Указывает контекст в текущем потоке во время общеязыковой среды выполнения (CLR) вызывает [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) метода или контекста, запрошенный в среде CLR при вызове [ IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2eba8-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="2eba8-109">Указывает контекст, в течение которого узел имеет привилегии более низкого уровня, таких как сборщик мусора, то есть конструктор класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="2eba8-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2eba8-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2eba8-110">Remarks</span></span>  
 <span data-ttu-id="2eba8-111">Среда CLR предоставляет один из `EContextType` значения как значение параметра в вызовах `IHostSecurityManager::GetSecurityContext` и `IHostSecurityManager::SetSecurityContext` методы.</span><span class="sxs-lookup"><span data-stu-id="2eba8-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2eba8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2eba8-112">Requirements</span></span>  
 <span data-ttu-id="2eba8-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2eba8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eba8-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2eba8-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2eba8-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2eba8-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2eba8-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2eba8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eba8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2eba8-117">See also</span></span>

- [<span data-ttu-id="2eba8-118">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="2eba8-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="2eba8-119">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="2eba8-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="2eba8-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="2eba8-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
