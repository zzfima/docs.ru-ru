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
ms.openlocfilehash: c8b03b96c8cab43046d109d0dd11ae135cb70c9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163614"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="8c09b-102">Метод ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="8c09b-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="8c09b-103">Получает поле третий адрес для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="8c09b-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="8c09b-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="8c09b-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c09b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c09b-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c09b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c09b-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8c09b-107">[out] Указатель на `ULONG32` , получающий третий адрес поля.</span><span class="sxs-lookup"><span data-stu-id="8c09b-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c09b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8c09b-108">Return Value</span></span>  
 <span data-ttu-id="8c09b-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8c09b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c09b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8c09b-110">Requirements</span></span>  
 <span data-ttu-id="8c09b-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8c09b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c09b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8c09b-112">See also</span></span>

- [<span data-ttu-id="8c09b-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="8c09b-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="8c09b-114">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="8c09b-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="8c09b-115">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="8c09b-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="8c09b-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="8c09b-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
