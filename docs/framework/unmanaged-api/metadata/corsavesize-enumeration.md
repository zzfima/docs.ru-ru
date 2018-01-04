---
title: "Перечисление CorSaveSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSaveSize
helpviewer_keywords: CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3780050285f63fa7334ec5463cd22050836dc136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="50b67-102">Перечисление CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="50b67-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="50b67-103">Содержит значения, указывающие уровень точности, необходимый при запросе размера операции сохранения.</span><span class="sxs-lookup"><span data-stu-id="50b67-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50b67-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50b67-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="50b67-105">Участники</span><span class="sxs-lookup"><span data-stu-id="50b67-105">Members</span></span>  
  
|<span data-ttu-id="50b67-106">Член</span><span class="sxs-lookup"><span data-stu-id="50b67-106">Member</span></span>|<span data-ttu-id="50b67-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="50b67-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="50b67-108">Указывает, что возвращаемое значение должно быть точным.</span><span class="sxs-lookup"><span data-stu-id="50b67-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="50b67-109">Указывает, что возвращаемое значение должно быть приблизительным.</span><span class="sxs-lookup"><span data-stu-id="50b67-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="50b67-110">Указывает, что удаляемые типы должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="50b67-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50b67-111">Требования</span><span class="sxs-lookup"><span data-stu-id="50b67-111">Requirements</span></span>  
 <span data-ttu-id="50b67-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50b67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50b67-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="50b67-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="50b67-114">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50b67-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50b67-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50b67-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b67-116">См. также</span><span class="sxs-lookup"><span data-stu-id="50b67-116">See Also</span></span>  
 [<span data-ttu-id="50b67-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="50b67-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
