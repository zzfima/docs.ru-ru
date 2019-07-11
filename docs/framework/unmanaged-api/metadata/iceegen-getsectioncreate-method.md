---
title: Метод ICeeGen::GetSectionCreate
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3de3a9c152f3074339dba330b7827cf795a7e537
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745975"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="9b59f-102">Метод ICeeGen::GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="9b59f-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="9b59f-103">Создает и возвращает раздел кода, используя указанные имя и значения флагов.</span><span class="sxs-lookup"><span data-stu-id="9b59f-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="9b59f-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="9b59f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b59f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b59f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b59f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b59f-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9b59f-107">[in] Указатель на строку, которая указывает имя создаваемого раздела.</span><span class="sxs-lookup"><span data-stu-id="9b59f-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="9b59f-108">[in] Флаги, определяющие параметры.</span><span class="sxs-lookup"><span data-stu-id="9b59f-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="9b59f-109">[out] Указатель на только что созданный код раздела.</span><span class="sxs-lookup"><span data-stu-id="9b59f-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b59f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b59f-110">Remarks</span></span>  
 <span data-ttu-id="9b59f-111">Вызовите `GetSectionCreate` только при наличии особых требований к разделам, которые не обрабатываются другими способами.</span><span class="sxs-lookup"><span data-stu-id="9b59f-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b59f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9b59f-112">Requirements</span></span>  
 <span data-ttu-id="9b59f-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b59f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b59f-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b59f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b59f-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b59f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b59f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b59f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b59f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9b59f-117">See also</span></span>

- [<span data-ttu-id="9b59f-118">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="9b59f-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
