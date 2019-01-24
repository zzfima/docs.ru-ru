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
ms.openlocfilehash: b460c2c4b0d38ec46ee9d7341de9b320a2ecaa7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594646"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="c14ca-102">Перечисление CorThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="c14ca-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="c14ca-103">Задает флаги для выбора параметров безопасности потока.</span><span class="sxs-lookup"><span data-stu-id="c14ca-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c14ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c14ca-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="c14ca-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c14ca-105">Members</span></span>  
  
|<span data-ttu-id="c14ca-106">Член</span><span class="sxs-lookup"><span data-stu-id="c14ca-106">Member</span></span>|<span data-ttu-id="c14ca-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="c14ca-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="c14ca-108">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c14ca-108">Default value.</span></span> <span data-ttu-id="c14ca-109">Эквивалентно `MDThreadSatetyOff`.</span><span class="sxs-lookup"><span data-stu-id="c14ca-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="c14ca-110">Указывает, что нельзя установить блокировку потоков чтения/записи.</span><span class="sxs-lookup"><span data-stu-id="c14ca-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="c14ca-111">Указывает, что блокировки потоков чтения/записи может быть задано.</span><span class="sxs-lookup"><span data-stu-id="c14ca-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c14ca-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c14ca-112">Requirements</span></span>  
 <span data-ttu-id="c14ca-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c14ca-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c14ca-114">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c14ca-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c14ca-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c14ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14ca-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c14ca-116">See also</span></span>
- [<span data-ttu-id="c14ca-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="c14ca-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
