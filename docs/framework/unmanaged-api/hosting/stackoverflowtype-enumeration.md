---
title: Перечисление StackOverflowType
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44d5b7fdb2908678671505649bb906c0c5f740e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751128"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="150fa-102">Перечисление StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="150fa-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="150fa-103">Содержит значения, указывающие на основную причину события переполнения стека.</span><span class="sxs-lookup"><span data-stu-id="150fa-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="150fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="150fa-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="150fa-105">Участники</span><span class="sxs-lookup"><span data-stu-id="150fa-105">Members</span></span>  
  
|<span data-ttu-id="150fa-106">Член</span><span class="sxs-lookup"><span data-stu-id="150fa-106">Member</span></span>|<span data-ttu-id="150fa-107">Описание</span><span class="sxs-lookup"><span data-stu-id="150fa-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="150fa-108">Переполнение стека было вызвано подсистему выполнения.</span><span class="sxs-lookup"><span data-stu-id="150fa-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="150fa-109">Переполнение стека было вызвано управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="150fa-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="150fa-110">Переполнение стека было вызвано неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="150fa-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="150fa-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="150fa-111">Remarks</span></span>  
 <span data-ttu-id="150fa-112">Эти сведения передаются на узел посредством вызова [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="150fa-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="150fa-113">Требования</span><span class="sxs-lookup"><span data-stu-id="150fa-113">Requirements</span></span>  
 <span data-ttu-id="150fa-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="150fa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="150fa-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="150fa-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="150fa-116">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="150fa-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="150fa-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="150fa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="150fa-118">См. также</span><span class="sxs-lookup"><span data-stu-id="150fa-118">See also</span></span>

- [<span data-ttu-id="150fa-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="150fa-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
