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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f756e8688299fbe9d53822851be83703f4aa6348
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550634"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="2a3a6-102">Перечисление CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="2a3a6-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="2a3a6-103">Содержит значения, указывающие уровень точности, необходимый при запросе размера операции сохранения.</span><span class="sxs-lookup"><span data-stu-id="2a3a6-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a3a6-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="2a3a6-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2a3a6-105">Members</span></span>  
  
|<span data-ttu-id="2a3a6-106">Член</span><span class="sxs-lookup"><span data-stu-id="2a3a6-106">Member</span></span>|<span data-ttu-id="2a3a6-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="2a3a6-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="2a3a6-108">Указывает, что возвращаемое значение должно быть точным.</span><span class="sxs-lookup"><span data-stu-id="2a3a6-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="2a3a6-109">Указывает, что возвращаемое значение должно быть приблизительным.</span><span class="sxs-lookup"><span data-stu-id="2a3a6-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="2a3a6-110">Указывает, что удаляемые типы должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="2a3a6-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a3a6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2a3a6-111">Requirements</span></span>  
 <span data-ttu-id="2a3a6-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a3a6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3a6-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2a3a6-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2a3a6-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a3a6-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a3a6-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3a6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3a6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2a3a6-116">See also</span></span>
- [<span data-ttu-id="2a3a6-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="2a3a6-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
