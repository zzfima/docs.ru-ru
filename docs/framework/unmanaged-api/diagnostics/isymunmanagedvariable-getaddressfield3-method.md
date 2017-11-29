---
title: "Метод ISymUnmanagedVariable::GetAddressField3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressField3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1dfeb3f02b0c767dfc200a625fa4c617692dc11f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="3e6ca-102">Метод ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="3e6ca-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="3e6ca-103">Возвращает третий адрес поля для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="3e6ca-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="3e6ca-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="3e6ca-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e6ca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e6ca-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e6ca-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e6ca-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3e6ca-107">[out] Указатель на `ULONG32` , который получает третий адрес поля.</span><span class="sxs-lookup"><span data-stu-id="3e6ca-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e6ca-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3e6ca-108">Return Value</span></span>  
 <span data-ttu-id="3e6ca-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="3e6ca-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e6ca-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3e6ca-110">Requirements</span></span>  
 <span data-ttu-id="3e6ca-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3e6ca-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6ca-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3e6ca-112">See Also</span></span>  
 [<span data-ttu-id="3e6ca-113">ISymUnmanagedVariable-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3e6ca-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="3e6ca-114">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="3e6ca-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="3e6ca-115">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="3e6ca-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="3e6ca-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="3e6ca-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
