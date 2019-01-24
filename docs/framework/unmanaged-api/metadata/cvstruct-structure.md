---
title: Структура CVStruct
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fb73980faa64464c572945fe5ad04e015dc8805b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720656"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="72e6b-102">Структура CVStruct</span><span class="sxs-lookup"><span data-stu-id="72e6b-102">CVStruct Structure</span></span>
<span data-ttu-id="72e6b-103">Содержит сведения, используемые при установке модуля или составного образа.</span><span class="sxs-lookup"><span data-stu-id="72e6b-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72e6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72e6b-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="72e6b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="72e6b-105">Members</span></span>  
  
|<span data-ttu-id="72e6b-106">Член</span><span class="sxs-lookup"><span data-stu-id="72e6b-106">Member</span></span>|<span data-ttu-id="72e6b-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="72e6b-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="72e6b-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="72e6b-108">Major</span></span>|<span data-ttu-id="72e6b-109">Номер основной версии сборки.</span><span class="sxs-lookup"><span data-stu-id="72e6b-109">Major version build number.</span></span>|  
|<span data-ttu-id="72e6b-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="72e6b-110">Minor</span></span>|<span data-ttu-id="72e6b-111">Дополнительный номер версии номер построения.</span><span class="sxs-lookup"><span data-stu-id="72e6b-111">Minor version build number.</span></span>|  
|<span data-ttu-id="72e6b-112">Sub</span><span class="sxs-lookup"><span data-stu-id="72e6b-112">Sub</span></span>|<span data-ttu-id="72e6b-113">Дополнительный номер сборки.</span><span class="sxs-lookup"><span data-stu-id="72e6b-113">Sub-build number.</span></span>|  
|<span data-ttu-id="72e6b-114">Построить</span><span class="sxs-lookup"><span data-stu-id="72e6b-114">Build</span></span>|<span data-ttu-id="72e6b-115">номер сборки.</span><span class="sxs-lookup"><span data-stu-id="72e6b-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72e6b-116">Требования</span><span class="sxs-lookup"><span data-stu-id="72e6b-116">Requirements</span></span>  
 <span data-ttu-id="72e6b-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72e6b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72e6b-118">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72e6b-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72e6b-119">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72e6b-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72e6b-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72e6b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e6b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="72e6b-121">See also</span></span>
- [<span data-ttu-id="72e6b-122">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="72e6b-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
