---
title: "Метод ICeeGen::GetSectionCreate"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionCreate
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2ea9cb20b62e1b1fa8e726ba0c49c5e24202530c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="39a85-102">Метод ICeeGen::GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="39a85-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="39a85-103">Создает и возвращает раздел кода с помощью указанного имени и значения флагов.</span><span class="sxs-lookup"><span data-stu-id="39a85-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="39a85-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="39a85-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a85-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39a85-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39a85-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="39a85-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="39a85-107">[in] Строка, указывающая имя раздела, чтобы создать указатель.</span><span class="sxs-lookup"><span data-stu-id="39a85-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="39a85-108">[in] Флаги, определяющие параметры.</span><span class="sxs-lookup"><span data-stu-id="39a85-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="39a85-109">[out] Указатель на только что созданный код раздела.</span><span class="sxs-lookup"><span data-stu-id="39a85-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39a85-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="39a85-110">Remarks</span></span>  
 <span data-ttu-id="39a85-111">Вызовите `GetSectionCreate` только при наличии особых требований к разделам, не обрабатываются другими способами.</span><span class="sxs-lookup"><span data-stu-id="39a85-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a85-112">Требования</span><span class="sxs-lookup"><span data-stu-id="39a85-112">Requirements</span></span>  
 <span data-ttu-id="39a85-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a85-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a85-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="39a85-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39a85-115">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39a85-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39a85-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a85-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a85-117">См. также</span><span class="sxs-lookup"><span data-stu-id="39a85-117">See Also</span></span>  
 [<span data-ttu-id="39a85-118">ICeeGen-интерфейс</span><span class="sxs-lookup"><span data-stu-id="39a85-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
