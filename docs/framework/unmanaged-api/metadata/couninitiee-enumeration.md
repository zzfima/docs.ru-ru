---
title: "Перечисление COUNINITIEE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COUNINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COUNINITIEE
helpviewer_keywords: COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 808320a2034011793429f1805edea82a52add23d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="d3d63-102">Перечисление COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="d3d63-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="d3d63-103">Указывает константы, используемые [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) при инициализации общеязыковая среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="d3d63-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3d63-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="d3d63-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d3d63-105">Members</span></span>  
  
|<span data-ttu-id="d3d63-106">Член</span><span class="sxs-lookup"><span data-stu-id="d3d63-106">Member</span></span>|<span data-ttu-id="d3d63-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="d3d63-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="d3d63-108">Указывает режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3d63-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="d3d63-109">Указывает режим отмены инициализации для выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="d3d63-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3d63-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d3d63-110">Requirements</span></span>  
 <span data-ttu-id="d3d63-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3d63-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3d63-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3d63-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3d63-113">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3d63-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3d63-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3d63-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d63-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d3d63-115">See Also</span></span>  
 [<span data-ttu-id="d3d63-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="d3d63-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
