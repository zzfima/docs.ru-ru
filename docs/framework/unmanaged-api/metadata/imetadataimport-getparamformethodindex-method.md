---
title: "Метод IMetaDataImport::GetParamForMethodIndex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamForMethodIndex
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cda4ffde7d38d74ddf7a81b6f0af4a556693094d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="16718-102">Метод IMetaDataImport::GetParamForMethodIndex</span><span class="sxs-lookup"><span data-stu-id="16718-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="16718-103">Возвращает токен, представляющий указанный параметр метода, представленного указанным токеном MethodDef.</span><span class="sxs-lookup"><span data-stu-id="16718-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16718-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16718-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16718-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16718-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="16718-106">[in] Токен, представляющий метод, чтобы возвратить маркер параметра для.</span><span class="sxs-lookup"><span data-stu-id="16718-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="16718-107">[in] Порядковая позиция в списке параметров, с которой происходит запрошенного параметра.</span><span class="sxs-lookup"><span data-stu-id="16718-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="16718-108">Параметры нумеруются, начиная с 1, возвращаемое значение метода в нулевой позиции.</span><span class="sxs-lookup"><span data-stu-id="16718-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="16718-109">[out] Указатель на токен ParamDef, который представляет запрошенный параметр.</span><span class="sxs-lookup"><span data-stu-id="16718-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16718-110">Требования</span><span class="sxs-lookup"><span data-stu-id="16718-110">Requirements</span></span>  
 <span data-ttu-id="16718-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16718-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16718-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="16718-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16718-113">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16718-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="16718-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16718-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16718-115">См. также</span><span class="sxs-lookup"><span data-stu-id="16718-115">See Also</span></span>  
 [<span data-ttu-id="16718-116">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="16718-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="16718-117">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="16718-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
