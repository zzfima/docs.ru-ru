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
ms.openlocfilehash: ef22114b582ebfc9714dedc0cb6e66594d945ca1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083794"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="ee555-102">Метод ICeeGen::GetStringSection</span><span class="sxs-lookup"><span data-stu-id="ee555-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="ee555-103">Получает строковое представление раздела кода, который ссылается указанный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="ee555-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="ee555-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="ee555-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee555-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee555-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee555-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee555-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="ee555-107">[in, out] Дескриптор раздела кода.</span><span class="sxs-lookup"><span data-stu-id="ee555-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee555-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ee555-108">Requirements</span></span>  
 <span data-ttu-id="ee555-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee555-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee555-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee555-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee555-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee555-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ee555-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ee555-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee555-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ee555-113">See also</span></span>

- [<span data-ttu-id="ee555-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="ee555-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
