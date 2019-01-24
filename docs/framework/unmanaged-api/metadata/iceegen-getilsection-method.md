---
title: Метод ICeeGen::GetIlSection
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e75f46d73e068c6bdaac6ae01740ecf589c97d42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635914"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="50021-102">Метод ICeeGen::GetIlSection</span><span class="sxs-lookup"><span data-stu-id="50021-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="50021-103">Получает раздел базовый код на промежуточном языке ссылается заданный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="50021-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="50021-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="50021-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50021-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50021-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50021-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="50021-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="50021-107">[in] Дескриптор раздела, чтобы получить.</span><span class="sxs-lookup"><span data-stu-id="50021-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50021-108">Требования</span><span class="sxs-lookup"><span data-stu-id="50021-108">Requirements</span></span>  
 <span data-ttu-id="50021-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50021-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50021-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="50021-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50021-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50021-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50021-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50021-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50021-113">См. также</span><span class="sxs-lookup"><span data-stu-id="50021-113">See also</span></span>
- [<span data-ttu-id="50021-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="50021-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
