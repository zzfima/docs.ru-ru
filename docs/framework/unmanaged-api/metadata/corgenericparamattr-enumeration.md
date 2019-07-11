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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 981829500e499be05a8de7c1ffb4683429a903e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781849"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="c62c6-102">Перечисление CorGenericParamAttr</span><span class="sxs-lookup"><span data-stu-id="c62c6-102">CorGenericParamAttr Enumeration</span></span>
<span data-ttu-id="c62c6-103">Содержит значения, описывающие <xref:System.Type> параметров для универсальных типов, использующихся в вызовах [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="c62c6-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c62c6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c62c6-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c62c6-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c62c6-105">Members</span></span>  
  
|<span data-ttu-id="c62c6-106">Член</span><span class="sxs-lookup"><span data-stu-id="c62c6-106">Member</span></span>|<span data-ttu-id="c62c6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c62c6-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="c62c6-108">Параметр Вариативность применяется только к универсальным параметрам для интерфейсов и делегатов.</span><span class="sxs-lookup"><span data-stu-id="c62c6-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="c62c6-109">Указывает на отсутствие дисперсии.</span><span class="sxs-lookup"><span data-stu-id="c62c6-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="c62c6-110">Указывает ковариации.</span><span class="sxs-lookup"><span data-stu-id="c62c6-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="c62c6-111">Указывает на контравариантность.</span><span class="sxs-lookup"><span data-stu-id="c62c6-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="c62c6-112">Особые ограничения могут применяться к любому <xref:System.Type> параметра.</span><span class="sxs-lookup"><span data-stu-id="c62c6-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="c62c6-113">Указывает, что ограничение не применяется к <xref:System.Type> параметра.</span><span class="sxs-lookup"><span data-stu-id="c62c6-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="c62c6-114">Указывает, что <xref:System.Type> параметр должен быть ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="c62c6-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="c62c6-115">Указывает, что <xref:System.Type> параметр должен иметь тип значения, который не может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="c62c6-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="c62c6-116">Указывает, что <xref:System.Type> параметр должен иметь открытый конструктор по умолчанию, который не принимает никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="c62c6-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c62c6-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c62c6-117">Requirements</span></span>  
 <span data-ttu-id="c62c6-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c62c6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c62c6-119">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c62c6-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c62c6-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c62c6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c62c6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c62c6-121">See also</span></span>

- [<span data-ttu-id="c62c6-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="c62c6-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
