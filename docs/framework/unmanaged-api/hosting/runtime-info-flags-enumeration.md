---
title: Перечисление RUNTIME_INFO_FLAGS
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e544db23abf89a20bd2f7763cfdb1256ea4a326c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="2a436-102">Перечисление RUNTIME_INFO_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2a436-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="2a436-103">Содержит значения, указывающие, какие сведения о среде (CLR) должны возвращаться.</span><span class="sxs-lookup"><span data-stu-id="2a436-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a436-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a436-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="2a436-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2a436-105">Members</span></span>  
  
|<span data-ttu-id="2a436-106">Член</span><span class="sxs-lookup"><span data-stu-id="2a436-106">Member</span></span>|<span data-ttu-id="2a436-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2a436-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="2a436-108">Указывает, что сведения о каталоге не будут включены.</span><span class="sxs-lookup"><span data-stu-id="2a436-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="2a436-109">Указывает, что сведения о версии не будут включены.</span><span class="sxs-lookup"><span data-stu-id="2a436-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="2a436-110">Указывает, что не нужно отображать диалоговое окно ошибки при сбое.</span><span class="sxs-lookup"><span data-stu-id="2a436-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="2a436-111">Указывает, что результаты вызова [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) функция с флагом SEM_FAILCRITICALERRORS должен быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="2a436-111">Indicates that the effects of calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="2a436-112">То есть диалоговое окно установки должен отображаться после сбоя, а не блокируются.</span><span class="sxs-lookup"><span data-stu-id="2a436-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="2a436-113">Указывает запрос для получения сведений об AMD-64-совместимые версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2a436-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="2a436-114">Указывает запрос для получения сведений об IA-64-совместимые версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2a436-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="2a436-115">Указывает запрос для получения сведений об x86-совместимой версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2a436-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="2a436-116">Указывает, что сведения об обновлении версии должны быть включены.</span><span class="sxs-lookup"><span data-stu-id="2a436-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a436-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a436-117">Remarks</span></span>  
 <span data-ttu-id="2a436-118">Следующие флаги архитектуры платформы можно указанного только по одному, а также нельзя использовать вместе:</span><span class="sxs-lookup"><span data-stu-id="2a436-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="2a436-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="2a436-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="2a436-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="2a436-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="2a436-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="2a436-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a436-122">Требования</span><span class="sxs-lookup"><span data-stu-id="2a436-122">Requirements</span></span>  
 <span data-ttu-id="2a436-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a436-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a436-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a436-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a436-125">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a436-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a436-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a436-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a436-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2a436-127">See Also</span></span>  
 [<span data-ttu-id="2a436-128">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="2a436-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
