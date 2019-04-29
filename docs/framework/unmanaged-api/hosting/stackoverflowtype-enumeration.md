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
ms.openlocfilehash: 8541ea7b614ff4a6ca666f0e2549a7f50e190192
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777992"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="0b37f-102">Перечисление StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="0b37f-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="0b37f-103">Содержит значения, указывающие на основную причину события переполнения стека.</span><span class="sxs-lookup"><span data-stu-id="0b37f-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b37f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b37f-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="0b37f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0b37f-105">Members</span></span>  
  
|<span data-ttu-id="0b37f-106">Член</span><span class="sxs-lookup"><span data-stu-id="0b37f-106">Member</span></span>|<span data-ttu-id="0b37f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0b37f-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="0b37f-108">Переполнение стека было вызвано подсистему выполнения.</span><span class="sxs-lookup"><span data-stu-id="0b37f-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="0b37f-109">Переполнение стека было вызвано управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0b37f-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="0b37f-110">Переполнение стека было вызвано неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0b37f-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b37f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b37f-111">Remarks</span></span>  
 <span data-ttu-id="0b37f-112">Эти сведения передаются на узел посредством вызова [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="0b37f-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b37f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0b37f-113">Requirements</span></span>  
 <span data-ttu-id="0b37f-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b37f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b37f-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b37f-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b37f-116">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b37f-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b37f-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b37f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b37f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0b37f-118">See also</span></span>

- [<span data-ttu-id="0b37f-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="0b37f-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
