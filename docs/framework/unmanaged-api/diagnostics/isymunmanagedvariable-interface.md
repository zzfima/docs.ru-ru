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
ms.openlocfilehash: 3db4fc691637c049e0374416cb92a2056555ad11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428704"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="67b2b-102">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="67b2b-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="67b2b-103">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="67b2b-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67b2b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="67b2b-104">Methods</span></span>  
  
|<span data-ttu-id="67b2b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="67b2b-105">Method</span></span>|<span data-ttu-id="67b2b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="67b2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67b2b-107">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="67b2b-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="67b2b-108">Получает поле первого адреса для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="67b2b-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="67b2b-109">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="67b2b-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="67b2b-110">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="67b2b-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="67b2b-111">Получает поле второго адреса для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="67b2b-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="67b2b-112">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="67b2b-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="67b2b-113">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="67b2b-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="67b2b-114">Возвращает третий адрес поля для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="67b2b-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="67b2b-115">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="67b2b-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="67b2b-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="67b2b-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="67b2b-117">Возвращает вид адрес этой переменной.</span><span class="sxs-lookup"><span data-stu-id="67b2b-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="67b2b-118">Метод GetAttributes</span><span class="sxs-lookup"><span data-stu-id="67b2b-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="67b2b-119">Получает флаги атрибутов для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="67b2b-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="67b2b-120">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="67b2b-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="67b2b-121">Возвращает конечное смещение переменной в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="67b2b-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="67b2b-122">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="67b2b-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="67b2b-123">Получает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="67b2b-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="67b2b-124">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="67b2b-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="67b2b-125">Возвращает подпись переменной.</span><span class="sxs-lookup"><span data-stu-id="67b2b-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="67b2b-126">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="67b2b-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="67b2b-127">Возвращает начальное смещение переменной в его родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="67b2b-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67b2b-128">Требования</span><span class="sxs-lookup"><span data-stu-id="67b2b-128">Requirements</span></span>  
 <span data-ttu-id="67b2b-129">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="67b2b-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b2b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="67b2b-130">See Also</span></span>  
 [<span data-ttu-id="67b2b-131">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="67b2b-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
