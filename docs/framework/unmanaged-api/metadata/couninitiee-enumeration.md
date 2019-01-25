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
ms.openlocfilehash: 475ae98d2bf7ea5132c9ec4555070f8bb2999cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744015"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="f913c-102">Перечисление COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="f913c-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="f913c-103">Задает константы, используемые [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) при инициализации среда CLR.</span><span class="sxs-lookup"><span data-stu-id="f913c-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f913c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f913c-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="f913c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f913c-105">Members</span></span>  
  
|<span data-ttu-id="f913c-106">Член</span><span class="sxs-lookup"><span data-stu-id="f913c-106">Member</span></span>|<span data-ttu-id="f913c-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="f913c-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="f913c-108">Указывает режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f913c-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="f913c-109">Указывает режим инициализации для выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="f913c-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f913c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f913c-110">Requirements</span></span>  
 <span data-ttu-id="f913c-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f913c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f913c-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f913c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f913c-113">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f913c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f913c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f913c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f913c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f913c-115">See also</span></span>
- [<span data-ttu-id="f913c-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="f913c-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
