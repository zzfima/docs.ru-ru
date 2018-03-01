---
title: "Перечисление CorGenericParamAttr"
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
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e40613d790baed5bd89bee1e1f5ca57043bfe76a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="503ee-102">Перечисление CorGenericParamAttr</span><span class="sxs-lookup"><span data-stu-id="503ee-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="503ee-103">Содержит значения, описывающие <xref:System.Type> параметры универсальных типов, использующихся в вызовах для [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="503ee-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="503ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="503ee-104">Syntax</span></span>  
  
```  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="503ee-105">Участники</span><span class="sxs-lookup"><span data-stu-id="503ee-105">Members</span></span>  
  
|<span data-ttu-id="503ee-106">Член</span><span class="sxs-lookup"><span data-stu-id="503ee-106">Member</span></span>|<span data-ttu-id="503ee-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="503ee-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="503ee-108">Дисперсия параметра применяется только к универсальным параметрам для интерфейсов и делегатов.</span><span class="sxs-lookup"><span data-stu-id="503ee-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="503ee-109">Указывает на отсутствие дисперсии.</span><span class="sxs-lookup"><span data-stu-id="503ee-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="503ee-110">Указывает на ковариацию.</span><span class="sxs-lookup"><span data-stu-id="503ee-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="503ee-111">Указывает на контравариантность.</span><span class="sxs-lookup"><span data-stu-id="503ee-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="503ee-112">Особые ограничения можно применить к любому <xref:System.Type> параметра.</span><span class="sxs-lookup"><span data-stu-id="503ee-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="503ee-113">Указывает, что ограничение не применяется к <xref:System.Type> параметра.</span><span class="sxs-lookup"><span data-stu-id="503ee-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="503ee-114">Указывает, что <xref:System.Type> параметр должен быть ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="503ee-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="503ee-115">Указывает, что <xref:System.Type> параметр должен быть типом значения, который не может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="503ee-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="503ee-116">Указывает, что <xref:System.Type> параметр должен иметь открытый конструктор по умолчанию, который не принимает никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="503ee-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="503ee-117">Требования</span><span class="sxs-lookup"><span data-stu-id="503ee-117">Requirements</span></span>  
 <span data-ttu-id="503ee-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="503ee-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="503ee-119">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="503ee-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="503ee-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="503ee-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="503ee-121">См. также</span><span class="sxs-lookup"><span data-stu-id="503ee-121">See Also</span></span>  
 [<span data-ttu-id="503ee-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="503ee-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
