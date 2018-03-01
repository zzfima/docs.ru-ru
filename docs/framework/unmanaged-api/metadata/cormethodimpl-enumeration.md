---
title: "Перечисление CorMethodImpl"
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
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e82eb50e4850ffbb4d5fc67d9603a3128cf8bcf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="4e564-102">Перечисление CorMethodImpl</span><span class="sxs-lookup"><span data-stu-id="4e564-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="4e564-103">Содержит значения, описывающие возможности реализации метода.</span><span class="sxs-lookup"><span data-stu-id="4e564-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e564-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e564-104">Syntax</span></span>  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="4e564-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4e564-105">Members</span></span>  
  
|<span data-ttu-id="4e564-106">Член</span><span class="sxs-lookup"><span data-stu-id="4e564-106">Member</span></span>|<span data-ttu-id="4e564-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="4e564-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="4e564-108">Флаги, описывающие тип кода.</span><span class="sxs-lookup"><span data-stu-id="4e564-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="4e564-109">Указывает, что реализация метода промежуточного языка Майкрософт (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4e564-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="4e564-110">Указывает, что для метода используется стандартная реализация.</span><span class="sxs-lookup"><span data-stu-id="4e564-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="4e564-111">Указывает, что реализация метода OPTIL.</span><span class="sxs-lookup"><span data-stu-id="4e564-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="4e564-112">Указывает, что реализация метода обеспечивается средой CLR.</span><span class="sxs-lookup"><span data-stu-id="4e564-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="4e564-113">Флаги, указывающие, является ли код является управляемым или неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="4e564-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="4e564-114">Указывает, что реализация метода является неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="4e564-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="4e564-115">Указывает, что метод реализуется как управляемый.</span><span class="sxs-lookup"><span data-stu-id="4e564-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="4e564-116">Указывает, что метод был определен.</span><span class="sxs-lookup"><span data-stu-id="4e564-116">Specifies that the method is defined.</span></span> <span data-ttu-id="4e564-117">Этот флаг используется главным образом в сценариях слияния.</span><span class="sxs-lookup"><span data-stu-id="4e564-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="4e564-118">Указывает, что подпись метода не может быть изменена для преобразования HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4e564-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="4e564-119">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="4e564-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="4e564-120">Указывает, что метод является однопотоковым выполнение основной части.</span><span class="sxs-lookup"><span data-stu-id="4e564-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="4e564-121">Указывает, что метод нельзя выполнять как встроенный.</span><span class="sxs-lookup"><span data-stu-id="4e564-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="4e564-122">Указывает, что метод должен быть встроенным по возможности.</span><span class="sxs-lookup"><span data-stu-id="4e564-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="4e564-123">Указывает, что метод не должен быть оптимизирован.</span><span class="sxs-lookup"><span data-stu-id="4e564-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="4e564-124">Максимальное допустимое значение для `CorMethodImpl`.</span><span class="sxs-lookup"><span data-stu-id="4e564-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e564-125">Требования</span><span class="sxs-lookup"><span data-stu-id="4e564-125">Requirements</span></span>  
 <span data-ttu-id="4e564-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e564-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e564-127">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4e564-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4e564-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e564-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e564-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4e564-129">See Also</span></span>  
 [<span data-ttu-id="4e564-130">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="4e564-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
