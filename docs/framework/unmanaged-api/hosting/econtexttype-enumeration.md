---
title: "Перечисление EContextType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EContextType
api_location: mscoree.dll
api_type: COM
f1_keywords: EContextType
helpviewer_keywords: EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73e6e9a1f1118a524b86b3711c0c7a6af4777f2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="09654-102">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="09654-102">EContextType Enumeration</span></span>
<span data-ttu-id="09654-103">Описывает контекст безопасности текущего потока.</span><span class="sxs-lookup"><span data-stu-id="09654-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09654-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09654-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="09654-105">Члены</span><span class="sxs-lookup"><span data-stu-id="09654-105">Members</span></span>  
  
|<span data-ttu-id="09654-106">Член</span><span class="sxs-lookup"><span data-stu-id="09654-106">Member</span></span>|<span data-ttu-id="09654-107">Описание</span><span class="sxs-lookup"><span data-stu-id="09654-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="09654-108">Указывает контекст в текущем потоке во время общеязыковая среда выполнения (CLR) вызывает [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) метода или контекста, запрошенный средой CLR в вызове [ IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="09654-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="09654-109">Указывает контекст, в течение которого узел должен иметь привилегии более низкого уровня, таких как сборщик мусора или конструктор класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="09654-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09654-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="09654-110">Remarks</span></span>  
 <span data-ttu-id="09654-111">Среда CLR предоставляет один из `EContextType` значения как значение параметра в вызовах `IHostSecurityManager::GetSecurityContext` и `IHostSecurityManager::SetSecurityContext` методы.</span><span class="sxs-lookup"><span data-stu-id="09654-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09654-112">Требования</span><span class="sxs-lookup"><span data-stu-id="09654-112">Requirements</span></span>  
 <span data-ttu-id="09654-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09654-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09654-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="09654-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09654-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09654-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09654-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09654-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09654-117">См. также</span><span class="sxs-lookup"><span data-stu-id="09654-117">See Also</span></span>  
 [<span data-ttu-id="09654-118">IHostSecurityContext-интерфейс</span><span class="sxs-lookup"><span data-stu-id="09654-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="09654-119">IHostSecurityManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="09654-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="09654-120">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="09654-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
