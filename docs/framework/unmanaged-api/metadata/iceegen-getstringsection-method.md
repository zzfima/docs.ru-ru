---
title: Метод ICeeGen::GetStringSection
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e306ccc824910226e522bc664f8f87f828a0d52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477053"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="c4a7b-102">Метод ICeeGen::GetStringSection</span><span class="sxs-lookup"><span data-stu-id="c4a7b-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="c4a7b-103">Получает строковое представление раздела кода, который ссылается указанный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="c4a7b-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="c4a7b-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="c4a7b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4a7b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4a7b-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4a7b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4a7b-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="c4a7b-107">[in, out] Дескриптор раздела кода.</span><span class="sxs-lookup"><span data-stu-id="c4a7b-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4a7b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c4a7b-108">Requirements</span></span>  
 <span data-ttu-id="c4a7b-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4a7b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4a7b-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c4a7b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4a7b-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4a7b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4a7b-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4a7b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a7b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c4a7b-113">See also</span></span>
- [<span data-ttu-id="c4a7b-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="c4a7b-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
