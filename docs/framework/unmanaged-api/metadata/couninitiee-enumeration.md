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
ms.openlocfilehash: e5cbd8c5b1bb048088fe137b1359d0bb9e29af20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176127"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="3f2a8-102">Перечисление COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="3f2a8-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="3f2a8-103">Определяет константы, используемые [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) при инициализации общего времени выполнения языка.</span><span class="sxs-lookup"><span data-stu-id="3f2a8-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f2a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f2a8-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="3f2a8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3f2a8-105">Members</span></span>  
  
|<span data-ttu-id="3f2a8-106">Участник</span><span class="sxs-lookup"><span data-stu-id="3f2a8-106">Member</span></span>|<span data-ttu-id="3f2a8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3f2a8-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="3f2a8-108">Указывает режим неинициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f2a8-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="3f2a8-109">Указывает режим неинициализации для разгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="3f2a8-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f2a8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3f2a8-110">Requirements</span></span>  
 <span data-ttu-id="3f2a8-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f2a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f2a8-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f2a8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f2a8-113">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f2a8-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f2a8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f2a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2a8-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3f2a8-115">See also</span></span>

- [<span data-ttu-id="3f2a8-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="3f2a8-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
