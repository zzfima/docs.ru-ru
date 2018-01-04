---
title: "Структура CVStruct"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CVStruct
api_location: mscoree.dll
api_type: COM
f1_keywords: CVStruct
helpviewer_keywords: CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e0c9087b180b39185fbf66235b515b9742e69ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cvstruct-structure"></a><span data-ttu-id="81e62-102">Структура CVStruct</span><span class="sxs-lookup"><span data-stu-id="81e62-102">CVStruct Structure</span></span>
<span data-ttu-id="81e62-103">Содержит сведения, используемые при установке модуля или составного образа.</span><span class="sxs-lookup"><span data-stu-id="81e62-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81e62-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81e62-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="81e62-105">Участники</span><span class="sxs-lookup"><span data-stu-id="81e62-105">Members</span></span>  
  
|<span data-ttu-id="81e62-106">Член</span><span class="sxs-lookup"><span data-stu-id="81e62-106">Member</span></span>|<span data-ttu-id="81e62-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="81e62-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="81e62-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="81e62-108">Major</span></span>|<span data-ttu-id="81e62-109">Номер основной версии сборки.</span><span class="sxs-lookup"><span data-stu-id="81e62-109">Major version build number.</span></span>|  
|<span data-ttu-id="81e62-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="81e62-110">Minor</span></span>|<span data-ttu-id="81e62-111">Номер построения дополнительной версии.</span><span class="sxs-lookup"><span data-stu-id="81e62-111">Minor version build number.</span></span>|  
|<span data-ttu-id="81e62-112">Sub</span><span class="sxs-lookup"><span data-stu-id="81e62-112">Sub</span></span>|<span data-ttu-id="81e62-113">Дополнительный номер сборки.</span><span class="sxs-lookup"><span data-stu-id="81e62-113">Sub-build number.</span></span>|  
|<span data-ttu-id="81e62-114">Построить</span><span class="sxs-lookup"><span data-stu-id="81e62-114">Build</span></span>|<span data-ttu-id="81e62-115">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="81e62-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81e62-116">Требования</span><span class="sxs-lookup"><span data-stu-id="81e62-116">Requirements</span></span>  
 <span data-ttu-id="81e62-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81e62-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81e62-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="81e62-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81e62-119">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81e62-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81e62-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81e62-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e62-121">См. также</span><span class="sxs-lookup"><span data-stu-id="81e62-121">See Also</span></span>  
 [<span data-ttu-id="81e62-122">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="81e62-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
