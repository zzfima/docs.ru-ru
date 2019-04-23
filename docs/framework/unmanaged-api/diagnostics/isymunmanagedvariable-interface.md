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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 712eca7f3f9fec9c81e638802f5a664ec6469d53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164350"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="2bda5-102">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="2bda5-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="2bda5-103">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="2bda5-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2bda5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2bda5-104">Methods</span></span>  
  
|<span data-ttu-id="2bda5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2bda5-105">Method</span></span>|<span data-ttu-id="2bda5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2bda5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2bda5-107">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="2bda5-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="2bda5-108">Получает поле первый адрес для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="2bda5-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="2bda5-109">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="2bda5-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="2bda5-110">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="2bda5-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="2bda5-111">Получает поле второго адреса для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="2bda5-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="2bda5-112">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="2bda5-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="2bda5-113">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="2bda5-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="2bda5-114">Получает поле третий адрес для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="2bda5-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="2bda5-115">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="2bda5-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="2bda5-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="2bda5-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="2bda5-117">Возвращает вид адрес этой переменной.</span><span class="sxs-lookup"><span data-stu-id="2bda5-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="2bda5-118">Метод GetAttributes</span><span class="sxs-lookup"><span data-stu-id="2bda5-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="2bda5-119">Возвращает флаги атрибутов для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="2bda5-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="2bda5-120">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="2bda5-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="2bda5-121">Возвращает конечное смещение переменной внутри родительского.</span><span class="sxs-lookup"><span data-stu-id="2bda5-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="2bda5-122">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="2bda5-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="2bda5-123">Возвращает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="2bda5-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="2bda5-124">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="2bda5-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="2bda5-125">Возвращает подпись переменной.</span><span class="sxs-lookup"><span data-stu-id="2bda5-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="2bda5-126">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="2bda5-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="2bda5-127">Возвращает начальное смещение переменной внутри родительского.</span><span class="sxs-lookup"><span data-stu-id="2bda5-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2bda5-128">Требования</span><span class="sxs-lookup"><span data-stu-id="2bda5-128">Requirements</span></span>  
 <span data-ttu-id="2bda5-129">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2bda5-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bda5-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2bda5-130">See also</span></span>

- [<span data-ttu-id="2bda5-131">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2bda5-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
