---
title: "Перечисление CorThreadSafetyOptions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorThreadSafetyOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorThreadSafetyOptions
helpviewer_keywords: CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccdd7fb2b97e98227a581b3b97783c2c47bcab1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="bb961-102">Перечисление CorThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="bb961-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="bb961-103">Задает флаги для выбора параметров безопасности потока.</span><span class="sxs-lookup"><span data-stu-id="bb961-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb961-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb961-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="bb961-105">Члены</span><span class="sxs-lookup"><span data-stu-id="bb961-105">Members</span></span>  
  
|<span data-ttu-id="bb961-106">Член</span><span class="sxs-lookup"><span data-stu-id="bb961-106">Member</span></span>|<span data-ttu-id="bb961-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bb961-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="bb961-108">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb961-108">Default value.</span></span> <span data-ttu-id="bb961-109">Эквивалентно `MDThreadSatetyOff`.</span><span class="sxs-lookup"><span data-stu-id="bb961-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="bb961-110">Указывает, что не сможет задать блокировку чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="bb961-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="bb961-111">Указывает, можно задать блокировку чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="bb961-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb961-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bb961-112">Requirements</span></span>  
 <span data-ttu-id="bb961-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb961-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb961-114">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="bb961-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bb961-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb961-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb961-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bb961-116">See Also</span></span>  
 [<span data-ttu-id="bb961-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="bb961-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
