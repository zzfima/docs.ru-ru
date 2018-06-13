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
ms.openlocfilehash: dd474c7f149b8eff542b674c2ba6527b6a0cbcb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427002"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="b3080-102">Метод ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="b3080-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="b3080-103">Возвращает третий адрес поля для данной переменной.</span><span class="sxs-lookup"><span data-stu-id="b3080-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="b3080-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="b3080-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3080-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3080-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3080-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3080-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b3080-107">[out] Указатель на `ULONG32` , который получает третий адрес поля.</span><span class="sxs-lookup"><span data-stu-id="b3080-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3080-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3080-108">Return Value</span></span>  
 <span data-ttu-id="b3080-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b3080-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3080-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b3080-110">Requirements</span></span>  
 <span data-ttu-id="b3080-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b3080-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3080-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b3080-112">See Also</span></span>  
 [<span data-ttu-id="b3080-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="b3080-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="b3080-114">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="b3080-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="b3080-115">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="b3080-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="b3080-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="b3080-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
