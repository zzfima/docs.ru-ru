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
ms.openlocfilehash: 9fca044b5dce260a1eed55b01531e7ae21a16ebd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446167"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="0ad2c-102">Метод IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="0ad2c-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="0ad2c-103">Возвращает указатель на токены метаданных для <xref:System.Type> , реализующий указанный метод, и для интерфейса, который объявляет этот метод.</span><span class="sxs-lookup"><span data-stu-id="0ad2c-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad2c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ad2c-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ad2c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ad2c-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="0ad2c-106">[in] Токен метаданных, представляющий метод для возврата маркеров для класса и интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0ad2c-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="0ad2c-107">[out] Токен метаданных, представляющий класс, реализующий метод.</span><span class="sxs-lookup"><span data-stu-id="0ad2c-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="0ad2c-108">[out] Токен метаданных, представляющий интерфейс, определяющий реализованный метод.</span><span class="sxs-lookup"><span data-stu-id="0ad2c-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad2c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="0ad2c-109">Requirements</span></span>  
 <span data-ttu-id="0ad2c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad2c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad2c-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ad2c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ad2c-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ad2c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ad2c-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad2c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad2c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0ad2c-114">See Also</span></span>  
 [<span data-ttu-id="0ad2c-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0ad2c-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="0ad2c-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0ad2c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
