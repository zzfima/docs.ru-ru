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
ms.openlocfilehash: 97aded59f880412a6a26e7e3d664c50ff1c2f103
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557413"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="b76a5-102">MALLOC_TYPE - перечисление</span><span class="sxs-lookup"><span data-stu-id="b76a5-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="b76a5-103">Содержит значения, определяющие характеристики выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="b76a5-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b76a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b76a5-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="b76a5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b76a5-105">Members</span></span>  
  
|<span data-ttu-id="b76a5-106">Член</span><span class="sxs-lookup"><span data-stu-id="b76a5-106">Member</span></span>|<span data-ttu-id="b76a5-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b76a5-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="b76a5-108">Используемый объем выделенной памяти может содержать исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="b76a5-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="b76a5-109">Используемый объем выделенной памяти является поточно ориентированной.</span><span class="sxs-lookup"><span data-stu-id="b76a5-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="b76a5-110">То есть память может осуществляться несколькими потоками без всякой синхронизации.</span><span class="sxs-lookup"><span data-stu-id="b76a5-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="b76a5-111">Если этот флаг не установлен, вызовы объекта должны быть сериализованы.</span><span class="sxs-lookup"><span data-stu-id="b76a5-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b76a5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b76a5-112">Requirements</span></span>  
 <span data-ttu-id="b76a5-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b76a5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b76a5-114">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b76a5-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b76a5-115">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b76a5-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b76a5-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b76a5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76a5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b76a5-117">See also</span></span>
- [<span data-ttu-id="b76a5-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="b76a5-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
