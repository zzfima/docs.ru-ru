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
ms.openlocfilehash: 9483cf8671b7d3ad5430081d93925af30b3d8368
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215694"
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="8a45e-102">Перечисление RUNTIME_INFO_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8a45e-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="8a45e-103">Содержит значения, указывающие, какие сведения об общеязыковой среде выполнения (CLR) должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="8a45e-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a45e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a45e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8a45e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="8a45e-105">Members</span></span>  
  
|<span data-ttu-id="8a45e-106">Член</span><span class="sxs-lookup"><span data-stu-id="8a45e-106">Member</span></span>|<span data-ttu-id="8a45e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8a45e-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="8a45e-108">Указывает, что сведения о каталоге не будут включены.</span><span class="sxs-lookup"><span data-stu-id="8a45e-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="8a45e-109">Указывает, что сведения о версии не следует включать.</span><span class="sxs-lookup"><span data-stu-id="8a45e-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="8a45e-110">Указывает, что диалоговое окно ошибки, не должны быть видны в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="8a45e-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="8a45e-111">Указывает, что последствия вызова [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) функция флаг SEM_FAILCRITICALERRORS, следует переопределить.</span><span class="sxs-lookup"><span data-stu-id="8a45e-111">Indicates that the effects of calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="8a45e-112">То есть диалоговое окно установки должен отображаться в случае сбоя, а не было подавлено.</span><span class="sxs-lookup"><span data-stu-id="8a45e-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="8a45e-113">Указывает запрос для получения сведений об AMD-64-совместимые версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a45e-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="8a45e-114">Указывает запрос для получения сведений об IA-64-совместимые версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a45e-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="8a45e-115">Указывает запрос для получения сведений об x86-совместимой версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a45e-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="8a45e-116">Указывает, что сведения об обновлении версии должны быть включены.</span><span class="sxs-lookup"><span data-stu-id="8a45e-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a45e-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a45e-117">Remarks</span></span>  
 <span data-ttu-id="8a45e-118">Далее перечислены флаги архитектуры платформы может быть указанного только один за другим и нельзя использовать вместе:</span><span class="sxs-lookup"><span data-stu-id="8a45e-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="8a45e-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="8a45e-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="8a45e-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="8a45e-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="8a45e-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="8a45e-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a45e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="8a45e-122">Requirements</span></span>  
 <span data-ttu-id="8a45e-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a45e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a45e-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a45e-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a45e-125">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a45e-125">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8a45e-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8a45e-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a45e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8a45e-127">See also</span></span>

- [<span data-ttu-id="8a45e-128">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="8a45e-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
