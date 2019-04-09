---
title: Метод ICeeGen::GetSectionDataLen
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca01f78cf46d4f7543b949c820eb6b1971687e23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198716"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="da2ee-102">Метод ICeeGen::GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="da2ee-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="da2ee-103">Получает длину указанного раздела.</span><span class="sxs-lookup"><span data-stu-id="da2ee-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="da2ee-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="da2ee-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2ee-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da2ee-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da2ee-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="da2ee-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="da2ee-107">[in] Раздел данных, длина которого будут извлекаться.</span><span class="sxs-lookup"><span data-stu-id="da2ee-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="da2ee-108">[out] Возвращаемая длина указанного раздела.</span><span class="sxs-lookup"><span data-stu-id="da2ee-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da2ee-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="da2ee-109">Remarks</span></span>  
 <span data-ttu-id="da2ee-110">Вызовите `GetSectionDataLen` только при наличии особых требований к разделам, которые не обрабатываются другими способами.</span><span class="sxs-lookup"><span data-stu-id="da2ee-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2ee-111">Требования</span><span class="sxs-lookup"><span data-stu-id="da2ee-111">Requirements</span></span>  
 <span data-ttu-id="da2ee-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da2ee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2ee-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="da2ee-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da2ee-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da2ee-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="da2ee-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="da2ee-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da2ee-116">См. также</span><span class="sxs-lookup"><span data-stu-id="da2ee-116">See also</span></span>

- [<span data-ttu-id="da2ee-117">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="da2ee-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
