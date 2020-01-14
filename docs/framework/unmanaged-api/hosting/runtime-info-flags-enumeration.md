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
ms.openlocfilehash: 9d505b917c343c40c7fa2a7aecf3466578ae0a8d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936639"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="f8907-102">Перечисление RUNTIME_INFO_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f8907-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="f8907-103">Содержит значения, которые указывают, какие сведения о среде CLR должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="f8907-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8907-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8907-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="f8907-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f8907-105">Members</span></span>  
  
|<span data-ttu-id="f8907-106">Член</span><span class="sxs-lookup"><span data-stu-id="f8907-106">Member</span></span>|<span data-ttu-id="f8907-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f8907-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="f8907-108">Указывает, что сведения о каталоге не следует включать.</span><span class="sxs-lookup"><span data-stu-id="f8907-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="f8907-109">Указывает, что сведения о версии указывать не следует.</span><span class="sxs-lookup"><span data-stu-id="f8907-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="f8907-110">Указывает, что при сбое не должно отображаться диалоговое окно ошибки.</span><span class="sxs-lookup"><span data-stu-id="f8907-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="f8907-111">Указывает, что эффекты вызова функции [функцию SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) с флагом SEM_FAILCRITICALERRORS должны быть переопределены.</span><span class="sxs-lookup"><span data-stu-id="f8907-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="f8907-112">То есть диалоговое окно установки должно отображаться при сбое, а не подавлено.</span><span class="sxs-lookup"><span data-stu-id="f8907-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="f8907-113">Указывает запрос сведений о версии среды выполнения, совместимой с AMD-64.</span><span class="sxs-lookup"><span data-stu-id="f8907-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="f8907-114">Указывает запрос сведений о версии среды выполнения, совместимой с IA-64.</span><span class="sxs-lookup"><span data-stu-id="f8907-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="f8907-115">Указывает запрос сведений о версии среды выполнения, совместимой с x86.</span><span class="sxs-lookup"><span data-stu-id="f8907-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="f8907-116">Указывает, что должны быть добавлены сведения об обновлении версии.</span><span class="sxs-lookup"><span data-stu-id="f8907-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8907-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="f8907-117">Remarks</span></span>  
 <span data-ttu-id="f8907-118">Следующие флаги архитектуры платформы могут быть указаны только один за раз и не могут быть объединены:</span><span class="sxs-lookup"><span data-stu-id="f8907-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="f8907-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="f8907-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="f8907-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="f8907-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="f8907-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="f8907-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8907-122">Требования</span><span class="sxs-lookup"><span data-stu-id="f8907-122">Requirements</span></span>  
 <span data-ttu-id="f8907-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8907-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8907-124">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f8907-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8907-125">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f8907-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8907-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8907-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8907-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8907-127">See also</span></span>

- [<span data-ttu-id="f8907-128">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="f8907-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
