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
ms.openlocfilehash: 6025b5914d4e96d10d83fc47a6baea7aa09605d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445148"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="7e116-102">Метод ICeeGen::GetIlSection</span><span class="sxs-lookup"><span data-stu-id="7e116-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="7e116-103">Получает раздел базовый код на промежуточном языке ссылается заданный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="7e116-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="7e116-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="7e116-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e116-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e116-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e116-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e116-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7e116-107">[in] Дескриптор раздела для получения.</span><span class="sxs-lookup"><span data-stu-id="7e116-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e116-108">Требования</span><span class="sxs-lookup"><span data-stu-id="7e116-108">Requirements</span></span>  
 <span data-ttu-id="7e116-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e116-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e116-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e116-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e116-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e116-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e116-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e116-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e116-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7e116-113">See Also</span></span>  
 [<span data-ttu-id="7e116-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="7e116-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
