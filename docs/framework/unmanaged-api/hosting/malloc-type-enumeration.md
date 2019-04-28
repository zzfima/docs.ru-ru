---
title: MALLOC_TYPE - перечисление
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765223"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="ca7ac-102">MALLOC_TYPE - перечисление</span><span class="sxs-lookup"><span data-stu-id="ca7ac-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="ca7ac-103">Содержит значения, определяющие характеристики выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="ca7ac-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca7ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca7ac-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="ca7ac-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ca7ac-105">Members</span></span>  
  
|<span data-ttu-id="ca7ac-106">Член</span><span class="sxs-lookup"><span data-stu-id="ca7ac-106">Member</span></span>|<span data-ttu-id="ca7ac-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ca7ac-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="ca7ac-108">Используемый объем выделенной памяти может содержать исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="ca7ac-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="ca7ac-109">Используемый объем выделенной памяти является поточно ориентированной.</span><span class="sxs-lookup"><span data-stu-id="ca7ac-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="ca7ac-110">То есть память может осуществляться несколькими потоками без всякой синхронизации.</span><span class="sxs-lookup"><span data-stu-id="ca7ac-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="ca7ac-111">Если этот флаг не установлен, вызовы объекта должны быть сериализованы.</span><span class="sxs-lookup"><span data-stu-id="ca7ac-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca7ac-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ca7ac-112">Requirements</span></span>  
 <span data-ttu-id="ca7ac-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca7ac-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca7ac-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca7ac-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca7ac-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca7ac-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca7ac-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca7ac-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7ac-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ca7ac-117">See also</span></span>

- [<span data-ttu-id="ca7ac-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="ca7ac-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
