---
title: Перечисление ASM_NAME
ms.date: 03/30/2017
api_name:
- ASM_NAME
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_NAME
helpviewer_keywords:
- ASM_NAME enumeration [.NET Framework fusion]
ms.assetid: c8b65b19-d777-428f-bc0c-0d84c78a37bc
topic_type:
- apiref
ms.openlocfilehash: 355f9da29a435a02d929cc01f28e95c4e04cdfcc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109157"
---
# <a name="asm_name-enumeration"></a><span data-ttu-id="16ca1-102">Перечисление ASM_NAME</span><span class="sxs-lookup"><span data-stu-id="16ca1-102">ASM_NAME Enumeration</span></span>
<span data-ttu-id="16ca1-103">Указывает версию, сборку, язык и региональные параметры, сигнатуру и т. д. для сборки, свойства которой будут извлечены или заданы методами [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="16ca1-103">Indicates the version, build, culture, signature, and so on, of the assembly whose properties will be retrieved or set by [IAssemblyName](iassemblyname-interface.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16ca1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16ca1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_NAME_PUBLIC_KEY = 0,  
    ASM_NAME_PUBLIC_KEY_TOKEN,  
    ASM_NAME_HASH_VALUE,  
    ASM_NAME_NAME,  
    ASM_NAME_MAJOR_VERSION,  
    ASM_NAME_MINOR_VERSION,  
    ASM_NAME_BUILD_NUMBER,  
    ASM_NAME_REVISION_NUMBER,  
    ASM_NAME_CULTURE,  
    ASM_NAME_PROCESSOR_ID_ARRAY,  
    ASM_NAME_OSINFO_ARRAY,  
    ASM_NAME_HASH_ALGID,  
    ASM_NAME_ALIAS,  
    ASM_NAME_CODEBASE_URL,  
    ASM_NAME_CODEBASE_LASTMOD,  
    ASM_NAME_NULL_PUBLIC_KEY,  
    ASM_NAME_NULL_PUBLIC_KEY_TOKEN,  
    ASM_NAME_CUSTOM,  
    ASM_NAME_NULL_CUSTOM,   
    ASM_NAME_MVID,  
    ASM_NAME_FILE_MAJOR_VERSION,  
    ASM_NAME_FILE_MINOR_VERSION,  
    ASM_NAME_FILE_BUILD_NUMBER,  
    ASM_NAME_FILE_REVISION_NUMBER,  
    ASM_NAME_RETARGET,  
    ASM_NAME_SIGNATURE_BLOB,  
    ASM_NAME_CONFIG_MASK,  
    ASM_NAME_ARCHITECTURE,  
    ASM_NAME_MAX_PARAMS  
  
} ASM_NAME;  
```  
  
## <a name="requirements"></a><span data-ttu-id="16ca1-105">Требования</span><span class="sxs-lookup"><span data-stu-id="16ca1-105">Requirements</span></span>  
 <span data-ttu-id="16ca1-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16ca1-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16ca1-107">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="16ca1-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="16ca1-108">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="16ca1-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="16ca1-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16ca1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ca1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="16ca1-110">See also</span></span>

- [<span data-ttu-id="16ca1-111">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="16ca1-111">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="16ca1-112">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="16ca1-112">Fusion Enumerations</span></span>](fusion-enumerations.md)
