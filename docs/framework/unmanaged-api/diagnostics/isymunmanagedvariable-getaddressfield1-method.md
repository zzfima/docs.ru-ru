---
title: Метод ISymUnmanagedVariable::GetAddressField1
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f9e0e234a8f77ef35ad93302fe8fc676cf9dbaeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427494"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="4d7e4-102">Метод ISymUnmanagedVariable::GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="4d7e4-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="4d7e4-103">Получает поле первого адреса для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="4d7e4-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="4d7e4-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="4d7e4-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d7e4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d7e4-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d7e4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d7e4-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4d7e4-107">[out] Указатель на `ULONG32` , который получает поле первого адреса.</span><span class="sxs-lookup"><span data-stu-id="4d7e4-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d7e4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4d7e4-108">Return Value</span></span>  
 <span data-ttu-id="4d7e4-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4d7e4-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d7e4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4d7e4-110">Requirements</span></span>  
 <span data-ttu-id="4d7e4-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4d7e4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7e4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4d7e4-112">See Also</span></span>  
 [<span data-ttu-id="4d7e4-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="4d7e4-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="4d7e4-114">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="4d7e4-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="4d7e4-115">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="4d7e4-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)  
 [<span data-ttu-id="4d7e4-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="4d7e4-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
