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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102951"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="f955e-102">Перечисление COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="f955e-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="f955e-103">Задает константы, используемые [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) при инициализации среда CLR.</span><span class="sxs-lookup"><span data-stu-id="f955e-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f955e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f955e-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="f955e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f955e-105">Members</span></span>  
  
|<span data-ttu-id="f955e-106">Член</span><span class="sxs-lookup"><span data-stu-id="f955e-106">Member</span></span>|<span data-ttu-id="f955e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f955e-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="f955e-108">Указывает режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f955e-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="f955e-109">Указывает режим инициализации для выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="f955e-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f955e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f955e-110">Requirements</span></span>  
 <span data-ttu-id="f955e-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f955e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f955e-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f955e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f955e-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f955e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f955e-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f955e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f955e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f955e-115">See also</span></span>

- [<span data-ttu-id="f955e-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="f955e-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
