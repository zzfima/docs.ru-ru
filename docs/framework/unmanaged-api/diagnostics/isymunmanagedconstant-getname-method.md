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
ms.openlocfilehash: 924feaeb91b42404461ad5d276c0cb77279d4dc4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449278"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="16ca9-102">Метод ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="16ca9-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="16ca9-103">Возвращает имя константы.</span><span class="sxs-lookup"><span data-stu-id="16ca9-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16ca9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16ca9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16ca9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="16ca9-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="16ca9-106">окне Длина буфера, на который указывает параметр `szName`.</span><span class="sxs-lookup"><span data-stu-id="16ca9-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="16ca9-107">заполняет Указатель на `ULONG32`, который получает размер (в символах) буфера, необходимого для хранения имени, включая завершающее пустое значение.</span><span class="sxs-lookup"><span data-stu-id="16ca9-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="16ca9-108">заполняет Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="16ca9-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16ca9-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="16ca9-109">Return Value</span></span>  
 <span data-ttu-id="16ca9-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="16ca9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16ca9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="16ca9-111">Requirements</span></span>  
 <span data-ttu-id="16ca9-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="16ca9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ca9-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="16ca9-113">See also</span></span>

- [<span data-ttu-id="16ca9-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="16ca9-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="16ca9-115">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="16ca9-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="16ca9-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="16ca9-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
