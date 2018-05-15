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
ms.openlocfilehash: 7a261d9164e8714531eab1fe9fc8148304e6d5bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="b14ff-102">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="b14ff-102">EContextType Enumeration</span></span>
<span data-ttu-id="b14ff-103">Описывает контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="b14ff-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b14ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b14ff-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="b14ff-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b14ff-105">Members</span></span>  
  
|<span data-ttu-id="b14ff-106">Член</span><span class="sxs-lookup"><span data-stu-id="b14ff-106">Member</span></span>|<span data-ttu-id="b14ff-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b14ff-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="b14ff-108">Указывает контекст в текущем потоке во время общеязыковая среда выполнения (CLR) вызывает [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) метода или контекста, запрошенный средой CLR в вызове [ IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="b14ff-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="b14ff-109">Указывает контекст, в течение которого узел должен иметь привилегии более низкого уровня, таких как сборщик мусора или конструктор класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="b14ff-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b14ff-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b14ff-110">Remarks</span></span>  
 <span data-ttu-id="b14ff-111">Среда CLR предоставляет один из `EContextType` значения как значение параметра в вызовах `IHostSecurityManager::GetSecurityContext` и `IHostSecurityManager::SetSecurityContext` методы.</span><span class="sxs-lookup"><span data-stu-id="b14ff-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b14ff-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b14ff-112">Requirements</span></span>  
 <span data-ttu-id="b14ff-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b14ff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b14ff-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b14ff-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b14ff-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b14ff-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b14ff-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b14ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14ff-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b14ff-117">See Also</span></span>  
 [<span data-ttu-id="b14ff-118">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="b14ff-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="b14ff-119">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="b14ff-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="b14ff-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="b14ff-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
