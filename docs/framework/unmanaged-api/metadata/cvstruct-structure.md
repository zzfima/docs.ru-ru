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
ms.openlocfilehash: 195f311d58f2169d715bb33986ee6e591622f377
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445047"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="ee5f2-102">Структура CVStruct</span><span class="sxs-lookup"><span data-stu-id="ee5f2-102">CVStruct Structure</span></span>
<span data-ttu-id="ee5f2-103">Содержит сведения, используемые при установке модуля или составного образа.</span><span class="sxs-lookup"><span data-stu-id="ee5f2-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee5f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee5f2-104">Syntax</span></span>  
  
```  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="ee5f2-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ee5f2-105">Members</span></span>  
  
|<span data-ttu-id="ee5f2-106">Член</span><span class="sxs-lookup"><span data-stu-id="ee5f2-106">Member</span></span>|<span data-ttu-id="ee5f2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ee5f2-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ee5f2-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="ee5f2-108">Major</span></span>|<span data-ttu-id="ee5f2-109">Номер основной версии сборки.</span><span class="sxs-lookup"><span data-stu-id="ee5f2-109">Major version build number.</span></span>|  
|<span data-ttu-id="ee5f2-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="ee5f2-110">Minor</span></span>|<span data-ttu-id="ee5f2-111">Номер построения дополнительной версии.</span><span class="sxs-lookup"><span data-stu-id="ee5f2-111">Minor version build number.</span></span>|  
|<span data-ttu-id="ee5f2-112">Sub</span><span class="sxs-lookup"><span data-stu-id="ee5f2-112">Sub</span></span>|<span data-ttu-id="ee5f2-113">Дополнительный номер сборки.</span><span class="sxs-lookup"><span data-stu-id="ee5f2-113">Sub-build number.</span></span>|  
|<span data-ttu-id="ee5f2-114">Построить</span><span class="sxs-lookup"><span data-stu-id="ee5f2-114">Build</span></span>|<span data-ttu-id="ee5f2-115">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="ee5f2-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee5f2-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ee5f2-116">Requirements</span></span>  
 <span data-ttu-id="ee5f2-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee5f2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee5f2-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee5f2-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee5f2-119">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee5f2-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee5f2-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee5f2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5f2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ee5f2-121">See Also</span></span>  
 [<span data-ttu-id="ee5f2-122">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="ee5f2-122">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
