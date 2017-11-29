---
title: "Перечисление CorFieldAttr"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorFieldAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorFieldAttr
helpviewer_keywords: CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b199764ea0fb2d02b01d7cf04d1fa8fad743109f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="7d37e-102">Перечисление CorFieldAttr</span><span class="sxs-lookup"><span data-stu-id="7d37e-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="7d37e-103">Содержит значения, описывающие метаданные поля.</span><span class="sxs-lookup"><span data-stu-id="7d37e-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d37e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d37e-104">Syntax</span></span>  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="7d37e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="7d37e-105">Members</span></span>  
  
|<span data-ttu-id="7d37e-106">Член</span><span class="sxs-lookup"><span data-stu-id="7d37e-106">Member</span></span>|<span data-ttu-id="7d37e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7d37e-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="7d37e-108">Указывает сведения о специальных возможностях.</span><span class="sxs-lookup"><span data-stu-id="7d37e-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="7d37e-109">Указывает, что поле не может ссылаться.</span><span class="sxs-lookup"><span data-stu-id="7d37e-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="7d37e-110">Указывает, что поле доступно только для родительского типа.</span><span class="sxs-lookup"><span data-stu-id="7d37e-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="7d37e-111">Указывает, что это поле доступно для производных классов в его сборке.</span><span class="sxs-lookup"><span data-stu-id="7d37e-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="7d37e-112">Указывает, что поле доступно для всех типов в его сборке.</span><span class="sxs-lookup"><span data-stu-id="7d37e-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="7d37e-113">Указывает, что поле доступно только для его типа и производных классов.</span><span class="sxs-lookup"><span data-stu-id="7d37e-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="7d37e-114">Указывает, что это поле доступно для производных классов и всех типов в его сборке.</span><span class="sxs-lookup"><span data-stu-id="7d37e-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="7d37e-115">Указывает, что поле доступно для всех типов с областью видимости данной области.</span><span class="sxs-lookup"><span data-stu-id="7d37e-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="7d37e-116">Указывает, что поле является членом его типа, а не членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7d37e-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="7d37e-117">Указывает, что поле нельзя изменить после его инициализации.</span><span class="sxs-lookup"><span data-stu-id="7d37e-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="7d37e-118">Указывает, что значение поля является константой во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="7d37e-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="7d37e-119">Указывает, что поле не сериализуется, если его тип является удаленным.</span><span class="sxs-lookup"><span data-stu-id="7d37e-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="7d37e-120">Указывает, что поле является специальным и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="7d37e-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="7d37e-121">Указывает, что реализация поля перенаправляется посредством PInvoke.</span><span class="sxs-lookup"><span data-stu-id="7d37e-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="7d37e-122">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="7d37e-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="7d37e-123">Указывает, что внутренние API метаданных среды CLR должны проверить кодировку имени.</span><span class="sxs-lookup"><span data-stu-id="7d37e-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="7d37e-124">Указывает, что поле содержит сведения о маршалинге.</span><span class="sxs-lookup"><span data-stu-id="7d37e-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="7d37e-125">Указывает, что поле имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d37e-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="7d37e-126">Указывает, что поле имеет относительный виртуальный адрес.</span><span class="sxs-lookup"><span data-stu-id="7d37e-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d37e-127">Требования</span><span class="sxs-lookup"><span data-stu-id="7d37e-127">Requirements</span></span>  
 <span data-ttu-id="7d37e-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d37e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d37e-129">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7d37e-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7d37e-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d37e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d37e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="7d37e-131">See Also</span></span>  
 [<span data-ttu-id="7d37e-132">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="7d37e-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
