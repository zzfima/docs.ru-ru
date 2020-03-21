---
title: Перечисление CorGenericParamAttr
ms.date: 03/30/2017
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
ms.openlocfilehash: bf0008ce9429671f0c156df4256bed0b2aaee184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176179"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="98262-102">Перечисление CorGenericParamAttr</span><span class="sxs-lookup"><span data-stu-id="98262-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="98262-103">Содержит значения, описывающие <xref:System.Type> параметры для генерических типов, используемые при вызовах на [IMetaDataEmit2::DefineGenericParam.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)</span><span class="sxs-lookup"><span data-stu-id="98262-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98262-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98262-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="98262-105">Члены</span><span class="sxs-lookup"><span data-stu-id="98262-105">Members</span></span>  
  
|<span data-ttu-id="98262-106">Участник</span><span class="sxs-lookup"><span data-stu-id="98262-106">Member</span></span>|<span data-ttu-id="98262-107">Описание</span><span class="sxs-lookup"><span data-stu-id="98262-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="98262-108">Разница параметров применяется только к общим параметрам для интерфейсов и делегатов.</span><span class="sxs-lookup"><span data-stu-id="98262-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="98262-109">Указывает на отсутствие дисперсии.</span><span class="sxs-lookup"><span data-stu-id="98262-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="98262-110">Указывает на коварность.</span><span class="sxs-lookup"><span data-stu-id="98262-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="98262-111">Указывает на противопоказания.</span><span class="sxs-lookup"><span data-stu-id="98262-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="98262-112">Специальные ограничения могут <xref:System.Type> применяться к любому параметру.</span><span class="sxs-lookup"><span data-stu-id="98262-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="98262-113">Означает, что к параметру <xref:System.Type> не применяется ограничение.</span><span class="sxs-lookup"><span data-stu-id="98262-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="98262-114">Означает, <xref:System.Type> что параметр должен быть эталонным типом.</span><span class="sxs-lookup"><span data-stu-id="98262-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="98262-115">Означает, <xref:System.Type> что параметр должен быть типом значения, который не может быть нулевая величина.</span><span class="sxs-lookup"><span data-stu-id="98262-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="98262-116">Означает, <xref:System.Type> что параметр должен иметь общедоступный конструктор по умолчанию, который не принимает никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="98262-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98262-117">Требования</span><span class="sxs-lookup"><span data-stu-id="98262-117">Requirements</span></span>  
 <span data-ttu-id="98262-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98262-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98262-119">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="98262-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="98262-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98262-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98262-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="98262-121">See also</span></span>

- [<span data-ttu-id="98262-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="98262-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
