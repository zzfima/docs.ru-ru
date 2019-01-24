---
title: Перечисление ASM_DISPLAY_FLAGS
ms.date: 03/30/2017
api_name:
- ASM_DISPLAY_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_DISPLAY_FLAGS
helpviewer_keywords:
- ASM_DISPLAY_FLAGS enumeration [.NET Framework fusion]
ms.assetid: dbade6c9-9d26-4a79-9fd2-46108edd12d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0871a06c6e27089d9e8fea6726d1d7b37fb75120
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561755"
---
# <a name="asmdisplayflags-enumeration"></a><span data-ttu-id="45275-102">Перечисление ASM_DISPLAY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="45275-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="45275-103">Указывает версию, сборки, язык и региональные параметры, подпись и т. д., сборки, отображаемое имя будет использоваться [IAssemblyName::GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="45275-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45275-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45275-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    ASM_DISPLAYF_VERSION                 = 0x01,  
    ASM_DISPLAYF_CULTURE                 = 0x02,  
    ASM_DISPLAYF_PUBLIC_KEY_TOKEN        = 0x04,  
    ASM_DISPLAYF_PUBLIC_KEY              = 0x08,  
    ASM_DISPLAYF_CUSTOM                  = 0x10,  
    ASM_DISPLAYF_PROCESSORARCHITECTURE   = 0x20,  
    ASM_DISPLAYF_LANGUAGEID              = 0x40,  
    ASM_DISPLAYF_RETARGET                = 0x80,  
    ASM_DISPLAYF_CONFIG_MASK             = 0x100,  
    ASM_DISPLAYF_MVID                    = 0x200,  
    ASM_DISPLAYF_FULL                    =   
                      ASM_DISPLAYF_VERSION           |   
                      ASM_DISPLAYF_CULTURE           |   
                      ASM_DISPLAYF_PUBLIC_KEY_TOKEN  |   
                      ASM_DISPLAYF_RETARGET          |   
                      ASM_DISPLAYF_PROCESSORARCHITECTURE  
  
} ASM_DISPLAY_FLAGS;  
```  
  
## <a name="remarks"></a><span data-ttu-id="45275-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="45275-105">Remarks</span></span>  
 <span data-ttu-id="45275-106">`ASM_DISPLAYF_FULL` отражает все изменения, внесенные в версию [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="45275-106">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span> <span data-ttu-id="45275-107">Не следует предполагать, что возвращаемое значение является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="45275-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45275-108">Требования</span><span class="sxs-lookup"><span data-stu-id="45275-108">Requirements</span></span>  
 <span data-ttu-id="45275-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45275-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45275-110">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="45275-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="45275-111">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45275-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45275-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45275-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45275-113">См. также</span><span class="sxs-lookup"><span data-stu-id="45275-113">See also</span></span>
- [<span data-ttu-id="45275-114">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="45275-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="45275-115">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="45275-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
