---
title: "Интерфейс ISymUnmanagedVariable"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable
helpviewer_keywords: ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c32d5b66c575a21b4d390cff560b71f93aa31927
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="bb929-102">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="bb929-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="bb929-103">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="bb929-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb929-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bb929-104">Methods</span></span>  
  
|<span data-ttu-id="bb929-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bb929-105">Method</span></span>|<span data-ttu-id="bb929-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bb929-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb929-107">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="bb929-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="bb929-108">Получает поле первого адреса для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="bb929-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="bb929-109">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="bb929-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="bb929-110">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="bb929-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="bb929-111">Получает поле второго адреса для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="bb929-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="bb929-112">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="bb929-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="bb929-113">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="bb929-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="bb929-114">Возвращает третий адрес поля для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="bb929-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="bb929-115">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="bb929-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="bb929-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="bb929-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="bb929-117">Возвращает вид адрес этой переменной.</span><span class="sxs-lookup"><span data-stu-id="bb929-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="bb929-118">Метод GetAttributes</span><span class="sxs-lookup"><span data-stu-id="bb929-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="bb929-119">Получает флаги атрибутов для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="bb929-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="bb929-120">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="bb929-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="bb929-121">Возвращает конечное смещение переменной в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="bb929-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="bb929-122">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="bb929-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="bb929-123">Получает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="bb929-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="bb929-124">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="bb929-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="bb929-125">Возвращает подпись переменной.</span><span class="sxs-lookup"><span data-stu-id="bb929-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="bb929-126">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="bb929-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="bb929-127">Возвращает начальное смещение переменной в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="bb929-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb929-128">Требования</span><span class="sxs-lookup"><span data-stu-id="bb929-128">Requirements</span></span>  
 <span data-ttu-id="bb929-129">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bb929-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb929-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bb929-130">See Also</span></span>  
 [<span data-ttu-id="bb929-131">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="bb929-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
