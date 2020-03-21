---
title: Перечисление CorSaveSize
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
ms.openlocfilehash: 13a4364244f7d0076d77d14c3e3ef161e3872bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176140"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="1d172-102">Перечисление CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="1d172-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="1d172-103">Содержит значения, указывающие уровень точности, необходимый при запросе размера операции сохранения.</span><span class="sxs-lookup"><span data-stu-id="1d172-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d172-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d172-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="1d172-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1d172-105">Members</span></span>  
  
|<span data-ttu-id="1d172-106">Участник</span><span class="sxs-lookup"><span data-stu-id="1d172-106">Member</span></span>|<span data-ttu-id="1d172-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1d172-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="1d172-108">Уточняется, что значение возврата должно быть точным.</span><span class="sxs-lookup"><span data-stu-id="1d172-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="1d172-109">Уточняется, что значение возврата должно быть оценено.</span><span class="sxs-lookup"><span data-stu-id="1d172-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="1d172-110">Указывается, что отбрасываемые типы должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="1d172-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d172-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1d172-111">Requirements</span></span>  
 <span data-ttu-id="1d172-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d172-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d172-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="1d172-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1d172-114">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d172-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d172-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d172-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d172-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1d172-116">See also</span></span>

- [<span data-ttu-id="1d172-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="1d172-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
