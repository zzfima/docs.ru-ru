---
title: Метод IMetaDataImport::GetNestedClassProps
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb5820087001a207af0c2552f91b4c17f5f78ff7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777661"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="425da-102">Метод IMetaDataImport::GetNestedClassProps</span><span class="sxs-lookup"><span data-stu-id="425da-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="425da-103">Возвращает токен TypeDef для родительского <xref:System.Type> заданного вложенного типа.</span><span class="sxs-lookup"><span data-stu-id="425da-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="425da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="425da-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="425da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="425da-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="425da-106">[in] TypeDef маркер, представляющий <xref:System.Type> для возврата родительского класса для токена.</span><span class="sxs-lookup"><span data-stu-id="425da-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="425da-107">[out] Указатель на токен TypeDef для <xref:System.Type> , `tdNestedClass` вложен в.</span><span class="sxs-lookup"><span data-stu-id="425da-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="425da-108">Требования</span><span class="sxs-lookup"><span data-stu-id="425da-108">Requirements</span></span>  
 <span data-ttu-id="425da-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="425da-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="425da-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="425da-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="425da-111">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="425da-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="425da-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="425da-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="425da-113">См. также</span><span class="sxs-lookup"><span data-stu-id="425da-113">See also</span></span>

- [<span data-ttu-id="425da-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="425da-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="425da-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="425da-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
