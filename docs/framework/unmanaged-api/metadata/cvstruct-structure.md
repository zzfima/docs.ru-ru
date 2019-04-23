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
ms.openlocfilehash: 4a5f06b3f79fed5dac5a6f07650e4fabd0aa5867
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142172"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="d7e97-102">Структура CVStruct</span><span class="sxs-lookup"><span data-stu-id="d7e97-102">CVStruct Structure</span></span>
<span data-ttu-id="d7e97-103">Содержит сведения, используемые при установке модуля или составного образа.</span><span class="sxs-lookup"><span data-stu-id="d7e97-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7e97-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="d7e97-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d7e97-105">Members</span></span>  
  
|<span data-ttu-id="d7e97-106">Член</span><span class="sxs-lookup"><span data-stu-id="d7e97-106">Member</span></span>|<span data-ttu-id="d7e97-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d7e97-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d7e97-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="d7e97-108">Major</span></span>|<span data-ttu-id="d7e97-109">Номер основной версии сборки.</span><span class="sxs-lookup"><span data-stu-id="d7e97-109">Major version build number.</span></span>|  
|<span data-ttu-id="d7e97-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="d7e97-110">Minor</span></span>|<span data-ttu-id="d7e97-111">Дополнительный номер версии номер построения.</span><span class="sxs-lookup"><span data-stu-id="d7e97-111">Minor version build number.</span></span>|  
|<span data-ttu-id="d7e97-112">Sub</span><span class="sxs-lookup"><span data-stu-id="d7e97-112">Sub</span></span>|<span data-ttu-id="d7e97-113">Дополнительный номер сборки.</span><span class="sxs-lookup"><span data-stu-id="d7e97-113">Sub-build number.</span></span>|  
|<span data-ttu-id="d7e97-114">Построить</span><span class="sxs-lookup"><span data-stu-id="d7e97-114">Build</span></span>|<span data-ttu-id="d7e97-115">номер сборки.</span><span class="sxs-lookup"><span data-stu-id="d7e97-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7e97-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d7e97-116">Requirements</span></span>  
 <span data-ttu-id="d7e97-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7e97-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e97-118">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7e97-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7e97-119">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d7e97-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7e97-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e97-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e97-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d7e97-121">See also</span></span>

- [<span data-ttu-id="d7e97-122">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="d7e97-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
