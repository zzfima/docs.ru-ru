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
ms.openlocfilehash: 3d8189365a73e85c0b9f5efb2aa03074385a3fb8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750749"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="bcfad-102">Перечисление COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="bcfad-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="bcfad-103">Задает константы, используемые [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) при инициализации среда CLR.</span><span class="sxs-lookup"><span data-stu-id="bcfad-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcfad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcfad-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="bcfad-105">Участники</span><span class="sxs-lookup"><span data-stu-id="bcfad-105">Members</span></span>  
  
|<span data-ttu-id="bcfad-106">Член</span><span class="sxs-lookup"><span data-stu-id="bcfad-106">Member</span></span>|<span data-ttu-id="bcfad-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bcfad-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="bcfad-108">Указывает режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bcfad-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="bcfad-109">Указывает режим инициализации для выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="bcfad-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bcfad-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bcfad-110">Requirements</span></span>  
 <span data-ttu-id="bcfad-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcfad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcfad-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bcfad-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bcfad-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bcfad-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bcfad-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcfad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfad-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bcfad-115">See also</span></span>

- [<span data-ttu-id="bcfad-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="bcfad-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
