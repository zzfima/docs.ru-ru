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
ms.openlocfilehash: f09c6bb79d7bd28f4d8b74237b6f343a07b79062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141471"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="9593c-102">Перечисление StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="9593c-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="9593c-103">Содержит значения, указывающие основную причину события переполнения стека.</span><span class="sxs-lookup"><span data-stu-id="9593c-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9593c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9593c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="9593c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="9593c-105">Members</span></span>  
  
|<span data-ttu-id="9593c-106">Член</span><span class="sxs-lookup"><span data-stu-id="9593c-106">Member</span></span>|<span data-ttu-id="9593c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9593c-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="9593c-108">Переполнение стека было вызвано подсистемой выполнения.</span><span class="sxs-lookup"><span data-stu-id="9593c-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="9593c-109">Переполнение стека было вызвано управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="9593c-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="9593c-110">Переполнение стека было вызвано неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="9593c-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9593c-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="9593c-111">Remarks</span></span>  
 <span data-ttu-id="9593c-112">Эти сведения передаются на узел посредством вызова метода [иактиононклревент:: oneven](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9593c-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9593c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9593c-113">Requirements</span></span>  
 <span data-ttu-id="9593c-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9593c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9593c-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9593c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9593c-116">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9593c-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9593c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9593c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9593c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9593c-118">See also</span></span>

- [<span data-ttu-id="9593c-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="9593c-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
