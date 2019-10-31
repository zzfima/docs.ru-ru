---
title: Перечисление HOST_TYPE
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: cc0cea10b4a209583fb7afb551a6b80d52ad7f62
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127032"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="962b5-102">Перечисление HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="962b5-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="962b5-103">Содержит значения, указывающие тип узла, запускающего приложение.</span><span class="sxs-lookup"><span data-stu-id="962b5-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="962b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="962b5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="962b5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="962b5-105">Members</span></span>  
  
|<span data-ttu-id="962b5-106">Член</span><span class="sxs-lookup"><span data-stu-id="962b5-106">Member</span></span>|<span data-ttu-id="962b5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="962b5-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="962b5-108">Запустите приложение из Апплаунч. exe.</span><span class="sxs-lookup"><span data-stu-id="962b5-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="962b5-109">Используйте это значение для частично доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="962b5-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="962b5-110">Запустите приложение напрямую.</span><span class="sxs-lookup"><span data-stu-id="962b5-110">Launch the application directly.</span></span> <span data-ttu-id="962b5-111">То есть запустите приложение из собственного EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="962b5-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="962b5-112">Используйте это значение для полностью доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="962b5-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="962b5-113">То же, что и HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="962b5-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="962b5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="962b5-114">Requirements</span></span>  
 <span data-ttu-id="962b5-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="962b5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="962b5-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="962b5-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="962b5-117">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="962b5-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="962b5-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="962b5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="962b5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="962b5-119">See also</span></span>

- [<span data-ttu-id="962b5-120">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="962b5-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
