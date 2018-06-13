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
ms.openlocfilehash: 2c5e970a1677b1e43821cce9985e32ebd0726686
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442544"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="db359-102">MALLOC_TYPE - перечисление</span><span class="sxs-lookup"><span data-stu-id="db359-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="db359-103">Содержит значения, указывающие характеристики выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="db359-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db359-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db359-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="db359-105">Участники</span><span class="sxs-lookup"><span data-stu-id="db359-105">Members</span></span>  
  
|<span data-ttu-id="db359-106">Член</span><span class="sxs-lookup"><span data-stu-id="db359-106">Member</span></span>|<span data-ttu-id="db359-107">Описание</span><span class="sxs-lookup"><span data-stu-id="db359-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="db359-108">Выделенная память может содержать исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="db359-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="db359-109">Выделенная память является потокобезопасной.</span><span class="sxs-lookup"><span data-stu-id="db359-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="db359-110">То есть память может осуществляться несколькими потоками без всякой синхронизации.</span><span class="sxs-lookup"><span data-stu-id="db359-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="db359-111">Если этот флаг не установлен, вызовы объекта должны быть сериализованы.</span><span class="sxs-lookup"><span data-stu-id="db359-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db359-112">Требования</span><span class="sxs-lookup"><span data-stu-id="db359-112">Requirements</span></span>  
 <span data-ttu-id="db359-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db359-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db359-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db359-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db359-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db359-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db359-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db359-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db359-117">См. также</span><span class="sxs-lookup"><span data-stu-id="db359-117">See Also</span></span>  
 [<span data-ttu-id="db359-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="db359-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
