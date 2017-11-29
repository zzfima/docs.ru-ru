---
title: "Перечисление CorMethodAttr"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodAttr
helpviewer_keywords: CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91afbc9894826b1f44d84f23b550a81d610e3de9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="bca9c-102">Перечисление CorMethodAttr</span><span class="sxs-lookup"><span data-stu-id="bca9c-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="bca9c-103">Содержит значения, описывающие функции метода.</span><span class="sxs-lookup"><span data-stu-id="bca9c-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bca9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bca9c-104">Syntax</span></span>  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="bca9c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="bca9c-105">Members</span></span>  
  
|<span data-ttu-id="bca9c-106">Член</span><span class="sxs-lookup"><span data-stu-id="bca9c-106">Member</span></span>|<span data-ttu-id="bca9c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bca9c-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="bca9c-108">Указывает доступ к членам.</span><span class="sxs-lookup"><span data-stu-id="bca9c-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="bca9c-109">Указывает, что элемент невозможно ссылаться.</span><span class="sxs-lookup"><span data-stu-id="bca9c-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="bca9c-110">Указывает, что член доступен только для родительского типа.</span><span class="sxs-lookup"><span data-stu-id="bca9c-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="bca9c-111">Указывает, что член доступен подтипов только в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="bca9c-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="bca9c-112">Указывает, что член доступен любой пользователь в сборке.</span><span class="sxs-lookup"><span data-stu-id="bca9c-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="bca9c-113">Указывает, что член доступен только для типа и подтипов.</span><span class="sxs-lookup"><span data-stu-id="bca9c-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="bca9c-114">Указывает, что член доступен для производных классов и других типов в его сборке.</span><span class="sxs-lookup"><span data-stu-id="bca9c-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="bca9c-115">Указывает, элемент доступен для всех типов с доступом к области.</span><span class="sxs-lookup"><span data-stu-id="bca9c-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="bca9c-116">Указывает, что член определен как часть типа, а не является членом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="bca9c-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="bca9c-117">Указывает, что метод не может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="bca9c-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="bca9c-118">Указывает, что метод может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="bca9c-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="bca9c-119">Указывает, что метод скрывает по имени и подписи, а не только по имени.</span><span class="sxs-lookup"><span data-stu-id="bca9c-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="bca9c-120">Задает макет виртуальной таблицы.</span><span class="sxs-lookup"><span data-stu-id="bca9c-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="bca9c-121">Указывает, использовать повторно ячейка, используемая для этого метода в виртуальной таблице.</span><span class="sxs-lookup"><span data-stu-id="bca9c-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="bca9c-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bca9c-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="bca9c-123">Указывает, что метод всегда получает новую ячейку в виртуальной таблице.</span><span class="sxs-lookup"><span data-stu-id="bca9c-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="bca9c-124">Указывает, что метод может быть переопределено те же типы, к которым она была видна.</span><span class="sxs-lookup"><span data-stu-id="bca9c-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="bca9c-125">Указывает, что метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="bca9c-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="bca9c-126">Указывает, что метод является специальным и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="bca9c-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="bca9c-127">Указывает, что реализация метода пересылается с помощью PInvoke.</span><span class="sxs-lookup"><span data-stu-id="bca9c-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="bca9c-128">Указывает, что метод является управляемый метод экспорте в неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="bca9c-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="bca9c-129">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="bca9c-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="bca9c-130">Указывает, что общеязыковая среда выполнения должна проверять кодировку имени метода.</span><span class="sxs-lookup"><span data-stu-id="bca9c-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="bca9c-131">Указывает, что метод имеет безопасности, связанные с ним.</span><span class="sxs-lookup"><span data-stu-id="bca9c-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="bca9c-132">Указывает, что метод вызывает другой метод, содержащий код безопасности.</span><span class="sxs-lookup"><span data-stu-id="bca9c-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bca9c-133">Требования</span><span class="sxs-lookup"><span data-stu-id="bca9c-133">Requirements</span></span>  
 <span data-ttu-id="bca9c-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bca9c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bca9c-135">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="bca9c-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bca9c-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bca9c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca9c-137">См. также</span><span class="sxs-lookup"><span data-stu-id="bca9c-137">See Also</span></span>  
 [<span data-ttu-id="bca9c-138">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="bca9c-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
