---
title: Интерфейс ISymUnmanagedVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: ee57ba14f048032e2cd9d0129089743c0f0304bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445973"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="887c7-102">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="887c7-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="887c7-103">Represents a variable, such as a parameter, a local variable, or a field.</span><span class="sxs-lookup"><span data-stu-id="887c7-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="887c7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="887c7-104">Methods</span></span>  
  
|<span data-ttu-id="887c7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="887c7-105">Method</span></span>|<span data-ttu-id="887c7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="887c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="887c7-107">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="887c7-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="887c7-108">Gets the first address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="887c7-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="887c7-109">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="887c7-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="887c7-110">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="887c7-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="887c7-111">Gets the second address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="887c7-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="887c7-112">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="887c7-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="887c7-113">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="887c7-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="887c7-114">Gets the third address field for this variable.</span><span class="sxs-lookup"><span data-stu-id="887c7-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="887c7-115">Its meaning depends on the kind of address.</span><span class="sxs-lookup"><span data-stu-id="887c7-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="887c7-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="887c7-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="887c7-117">Gets the kind of address of this variable.</span><span class="sxs-lookup"><span data-stu-id="887c7-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="887c7-118">Метод GetAttributes</span><span class="sxs-lookup"><span data-stu-id="887c7-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="887c7-119">Gets the attribute flags for this variable.</span><span class="sxs-lookup"><span data-stu-id="887c7-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="887c7-120">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="887c7-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="887c7-121">Gets the end offset of this variable within its parent.</span><span class="sxs-lookup"><span data-stu-id="887c7-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="887c7-122">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="887c7-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="887c7-123">Gets the name of this variable.</span><span class="sxs-lookup"><span data-stu-id="887c7-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="887c7-124">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="887c7-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="887c7-125">Gets the signature of this variable.</span><span class="sxs-lookup"><span data-stu-id="887c7-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="887c7-126">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="887c7-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="887c7-127">Gets the start offset of this variable within its parent.</span><span class="sxs-lookup"><span data-stu-id="887c7-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="887c7-128">Требования</span><span class="sxs-lookup"><span data-stu-id="887c7-128">Requirements</span></span>  
 <span data-ttu-id="887c7-129">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="887c7-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887c7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="887c7-130">See also</span></span>

- [<span data-ttu-id="887c7-131">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="887c7-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
