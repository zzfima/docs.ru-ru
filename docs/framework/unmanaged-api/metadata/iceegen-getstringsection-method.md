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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083794"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="b9aa4-102">Метод ICeeGen::GetStringSection</span><span class="sxs-lookup"><span data-stu-id="b9aa4-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="b9aa4-103">Получает строковое представление раздела кода, который ссылается указанный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="b9aa4-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9aa4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9aa4-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9aa4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9aa4-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b9aa4-107">[in, out] Дескриптор раздела кода.</span><span class="sxs-lookup"><span data-stu-id="b9aa4-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9aa4-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b9aa4-108">Requirements</span></span>  
 <span data-ttu-id="b9aa4-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9aa4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9aa4-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b9aa4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9aa4-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9aa4-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9aa4-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9aa4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9aa4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b9aa4-113">See also</span></span>

- [<span data-ttu-id="b9aa4-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="b9aa4-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
