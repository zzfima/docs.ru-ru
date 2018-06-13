---
title: Перечисление CorThreadSafetyOptions
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3407fcac420b8129dd39eabf84aec84b58651944
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442849"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="61cc8-102">Перечисление CorThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="61cc8-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="61cc8-103">Задает флаги для выбора параметров безопасности потока.</span><span class="sxs-lookup"><span data-stu-id="61cc8-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61cc8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61cc8-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="61cc8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="61cc8-105">Members</span></span>  
  
|<span data-ttu-id="61cc8-106">Член</span><span class="sxs-lookup"><span data-stu-id="61cc8-106">Member</span></span>|<span data-ttu-id="61cc8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="61cc8-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="61cc8-108">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61cc8-108">Default value.</span></span> <span data-ttu-id="61cc8-109">Эквивалентно `MDThreadSatetyOff`.</span><span class="sxs-lookup"><span data-stu-id="61cc8-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="61cc8-110">Указывает, что не сможет задать блокировку чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="61cc8-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="61cc8-111">Указывает, можно задать блокировку чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="61cc8-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61cc8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="61cc8-112">Requirements</span></span>  
 <span data-ttu-id="61cc8-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61cc8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61cc8-114">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="61cc8-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="61cc8-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61cc8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cc8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="61cc8-116">See Also</span></span>  
 [<span data-ttu-id="61cc8-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="61cc8-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
