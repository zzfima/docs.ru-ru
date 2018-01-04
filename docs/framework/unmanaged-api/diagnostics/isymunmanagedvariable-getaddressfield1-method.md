---
title: "Метод ISymUnmanagedVariable::GetAddressField1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressField1
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8085deb0cdb0b16eddfa39663277ceecdde10341
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="b45ec-102">Метод ISymUnmanagedVariable::GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="b45ec-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="b45ec-103">Получает поле первого адреса для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="b45ec-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="b45ec-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="b45ec-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b45ec-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b45ec-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b45ec-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b45ec-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b45ec-107">[out] Указатель на `ULONG32` , который получает поле первого адреса.</span><span class="sxs-lookup"><span data-stu-id="b45ec-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b45ec-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b45ec-108">Return Value</span></span>  
 <span data-ttu-id="b45ec-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b45ec-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b45ec-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b45ec-110">Requirements</span></span>  
 <span data-ttu-id="b45ec-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b45ec-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b45ec-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b45ec-112">See Also</span></span>  
 [<span data-ttu-id="b45ec-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="b45ec-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="b45ec-114">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="b45ec-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="b45ec-115">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="b45ec-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)  
 [<span data-ttu-id="b45ec-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="b45ec-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
