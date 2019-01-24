---
title: Метод ISymUnmanagedVariable::GetAddressField3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c2695fb6fcd0f4bba3576f2331c80961e9a444d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649184"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="b6096-102">Метод ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="b6096-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="b6096-103">Получает поле третий адрес для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="b6096-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="b6096-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="b6096-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6096-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6096-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6096-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6096-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b6096-107">[out] Указатель на `ULONG32` , получающий третий адрес поля.</span><span class="sxs-lookup"><span data-stu-id="b6096-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6096-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b6096-108">Return Value</span></span>  
 <span data-ttu-id="b6096-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6096-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6096-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b6096-110">Requirements</span></span>  
 <span data-ttu-id="b6096-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6096-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6096-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b6096-112">See also</span></span>
- [<span data-ttu-id="b6096-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="b6096-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="b6096-114">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="b6096-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="b6096-115">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="b6096-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="b6096-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="b6096-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
