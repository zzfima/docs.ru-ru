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
ms.openlocfilehash: 5e82f542bdc364a52fc558e582134a7d8d554ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131144"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="bdf79-102">Перечисление EContextType</span><span class="sxs-lookup"><span data-stu-id="bdf79-102">EContextType Enumeration</span></span>
<span data-ttu-id="bdf79-103">Описывает контекст безопасности выполняющегося в данный момент потока.</span><span class="sxs-lookup"><span data-stu-id="bdf79-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdf79-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="bdf79-105">Члены</span><span class="sxs-lookup"><span data-stu-id="bdf79-105">Members</span></span>  
  
|<span data-ttu-id="bdf79-106">Член</span><span class="sxs-lookup"><span data-stu-id="bdf79-106">Member</span></span>|<span data-ttu-id="bdf79-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bdf79-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="bdf79-108">Указывает контекст текущего потока во время вызова средой CLR метода [IHostSecurityManager:: getsecuritycontext-](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) или контекста, ЗАПРАШИВАЕМого средой CLR при вызове [IHostSecurityManager:: SetSecurityContext ](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)метод.</span><span class="sxs-lookup"><span data-stu-id="bdf79-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="bdf79-109">Указывает контекст, для которого узел имеет более низкий уровень привилегий, например сборщик мусора, конструктор класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="bdf79-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdf79-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="bdf79-110">Remarks</span></span>  
 <span data-ttu-id="bdf79-111">Среда CLR предоставляет одно из значений `EContextType` в качестве значения параметра в вызовах методов `IHostSecurityManager::GetSecurityContext` и `IHostSecurityManager::SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="bdf79-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf79-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bdf79-112">Requirements</span></span>  
 <span data-ttu-id="bdf79-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdf79-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf79-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bdf79-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bdf79-115">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bdf79-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bdf79-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdf79-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf79-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bdf79-117">See also</span></span>

- [<span data-ttu-id="bdf79-118">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="bdf79-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="bdf79-119">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="bdf79-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="bdf79-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="bdf79-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
