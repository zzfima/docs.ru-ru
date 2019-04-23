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
ms.openlocfilehash: bc36468a2016822e884ec3a36a23c75477a00a2d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217202"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="ce7f1-102">Перечисление CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="ce7f1-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="ce7f1-103">Содержит значения, указывающие уровень точности, необходимый при запросе размера операции сохранения.</span><span class="sxs-lookup"><span data-stu-id="ce7f1-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce7f1-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="ce7f1-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ce7f1-105">Members</span></span>  
  
|<span data-ttu-id="ce7f1-106">Член</span><span class="sxs-lookup"><span data-stu-id="ce7f1-106">Member</span></span>|<span data-ttu-id="ce7f1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ce7f1-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="ce7f1-108">Указывает, что возвращаемое значение должно быть точным.</span><span class="sxs-lookup"><span data-stu-id="ce7f1-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="ce7f1-109">Указывает, что возвращаемое значение должно быть приблизительным.</span><span class="sxs-lookup"><span data-stu-id="ce7f1-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="ce7f1-110">Указывает, что удаляемые типы должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="ce7f1-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce7f1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ce7f1-111">Requirements</span></span>  
 <span data-ttu-id="ce7f1-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce7f1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7f1-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ce7f1-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ce7f1-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce7f1-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce7f1-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce7f1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7f1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ce7f1-116">See also</span></span>

- [<span data-ttu-id="ce7f1-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ce7f1-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
