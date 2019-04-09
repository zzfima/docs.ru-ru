---
title: Перечисление CeeSectionAttr
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c317524cefd7ed654e76bdd7051cdcd7653062db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101794"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="d8ef8-102">Перечисление CeeSectionAttr</span><span class="sxs-lookup"><span data-stu-id="d8ef8-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="d8ef8-103">Предоставляет значения, задающие атрибуты раздела для использования [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ef8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8ef8-104">Syntax</span></span>  
  
```  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="d8ef8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d8ef8-105">Members</span></span>  
  
|<span data-ttu-id="d8ef8-106">Член</span><span class="sxs-lookup"><span data-stu-id="d8ef8-106">Member</span></span>|<span data-ttu-id="d8ef8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d8ef8-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="d8ef8-108">Раздел не имеет атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="d8ef8-109">Раздел содержит инициализированные данные, которые можно будет только для чтения, не обновляется.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="d8ef8-110">Раздел содержит инициализированные данные, который может читать или обновлены.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="d8ef8-111">Раздел содержит исполняемый код, который может быть прочитан и исполнен.</span><span class="sxs-lookup"><span data-stu-id="d8ef8-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8ef8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d8ef8-112">Requirements</span></span>  
 <span data-ttu-id="d8ef8-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8ef8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8ef8-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d8ef8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8ef8-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8ef8-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d8ef8-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d8ef8-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8ef8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d8ef8-117">See also</span></span>

- [<span data-ttu-id="d8ef8-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="d8ef8-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
