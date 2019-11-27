---
title: Метод IMetaDataImport::GetModuleFromScope
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 026a952e14cda2ef4ebc32ca91006026e920e3c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437355"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="4d41b-102">Метод IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="4d41b-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="4d41b-103">Возвращает маркер метаданных для модуля, на который ссылается текущая область метаданных.</span><span class="sxs-lookup"><span data-stu-id="4d41b-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d41b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d41b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d41b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d41b-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="4d41b-106">заполняет Указатель на маркер, представляющий модуль, на который ссылается текущая область метаданных.</span><span class="sxs-lookup"><span data-stu-id="4d41b-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d41b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4d41b-107">Requirements</span></span>  
 <span data-ttu-id="4d41b-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d41b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d41b-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="4d41b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d41b-110">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4d41b-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4d41b-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d41b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d41b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4d41b-112">See also</span></span>

- [<span data-ttu-id="4d41b-113">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4d41b-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4d41b-114">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4d41b-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
