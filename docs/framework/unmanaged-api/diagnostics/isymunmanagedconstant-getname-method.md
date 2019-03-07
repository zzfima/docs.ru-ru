---
title: Метод ISymUnmanagedConstant::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e57ab385ce4d393b29ff5af867bf7a019bf2b824
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478938"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="4f64e-102">Метод ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="4f64e-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="4f64e-103">Возвращает имя константы.</span><span class="sxs-lookup"><span data-stu-id="4f64e-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f64e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f64e-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f64e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f64e-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="4f64e-106">[in] Длина буфера, `szName` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="4f64e-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4f64e-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения имени, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="4f64e-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="4f64e-108">[out] Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="4f64e-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f64e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4f64e-109">Return Value</span></span>  
 <span data-ttu-id="4f64e-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4f64e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f64e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4f64e-111">Requirements</span></span>  
 <span data-ttu-id="4f64e-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4f64e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f64e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4f64e-113">See also</span></span>
- [<span data-ttu-id="4f64e-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="4f64e-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="4f64e-115">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="4f64e-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="4f64e-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="4f64e-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
