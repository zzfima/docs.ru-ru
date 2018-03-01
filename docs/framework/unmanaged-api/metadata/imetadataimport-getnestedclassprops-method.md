---
title: "Метод IMetaDataImport::GetNestedClassProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8bbfe382a9a2fdf8ece1015ee73c3d9ef604ec7e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="7a88f-102">Метод IMetaDataImport::GetNestedClassProps</span><span class="sxs-lookup"><span data-stu-id="7a88f-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="7a88f-103">Возвращает токен TypeDef для родительского <xref:System.Type> заданного вложенного типа.</span><span class="sxs-lookup"><span data-stu-id="7a88f-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a88f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a88f-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a88f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7a88f-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="7a88f-106">[in] TypeDef маркер, представляющий <xref:System.Type> для возврата родительского класса для токена.</span><span class="sxs-lookup"><span data-stu-id="7a88f-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="7a88f-107">[out] Указатель на токен TypeDef для <xref:System.Type> , `tdNestedClass` является вложенным в.</span><span class="sxs-lookup"><span data-stu-id="7a88f-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a88f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="7a88f-108">Requirements</span></span>  
 <span data-ttu-id="7a88f-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a88f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a88f-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7a88f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a88f-111">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a88f-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a88f-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a88f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a88f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7a88f-113">See Also</span></span>  
 [<span data-ttu-id="7a88f-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7a88f-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7a88f-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7a88f-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
