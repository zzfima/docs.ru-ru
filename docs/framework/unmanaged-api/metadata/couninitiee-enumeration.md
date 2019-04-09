---
title: Перечисление COUNINITIEE
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cf1bfa03fd14d6324af60781003a8072a267a7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102951"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="e0455-102">Перечисление COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="e0455-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="e0455-103">Задает константы, используемые [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) при инициализации среда CLR.</span><span class="sxs-lookup"><span data-stu-id="e0455-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0455-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0455-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="e0455-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e0455-105">Members</span></span>  
  
|<span data-ttu-id="e0455-106">Член</span><span class="sxs-lookup"><span data-stu-id="e0455-106">Member</span></span>|<span data-ttu-id="e0455-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e0455-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="e0455-108">Указывает режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0455-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="e0455-109">Указывает режим инициализации для выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="e0455-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0455-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e0455-110">Requirements</span></span>  
 <span data-ttu-id="e0455-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0455-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0455-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e0455-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0455-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0455-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e0455-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e0455-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0455-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e0455-115">See also</span></span>

- [<span data-ttu-id="e0455-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="e0455-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
