---
title: Метод IMetaDataImport::GetInterfaceImplProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91cb42a5bf1115de82b5fe28693cb77b66915c9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600562"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="7bcd4-102">Метод IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="7bcd4-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="7bcd4-103">Возвращает указатель на токены метаданных для <xref:System.Type> , реализующий заданный метод, и для интерфейса, который объявляет этот метод.</span><span class="sxs-lookup"><span data-stu-id="7bcd4-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bcd4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bcd4-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7bcd4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7bcd4-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="7bcd4-106">[in] Токен метаданных, представляющий метод для возврата маркеров для класса и интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7bcd4-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="7bcd4-107">[out] Токен метаданных, представляющий класс, который реализует метод.</span><span class="sxs-lookup"><span data-stu-id="7bcd4-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="7bcd4-108">[out] Токен метаданных, представляющий интерфейс, определяющий метод, реализованный.</span><span class="sxs-lookup"><span data-stu-id="7bcd4-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bcd4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7bcd4-109">Requirements</span></span>  
 <span data-ttu-id="7bcd4-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bcd4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bcd4-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7bcd4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7bcd4-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7bcd4-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7bcd4-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bcd4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bcd4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7bcd4-114">See also</span></span>
- [<span data-ttu-id="7bcd4-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7bcd4-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7bcd4-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7bcd4-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
