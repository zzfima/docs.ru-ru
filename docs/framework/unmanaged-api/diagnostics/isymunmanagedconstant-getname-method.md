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
ms.openlocfilehash: 1da8d89cf9ae2eed7b846774434d6ea472afbb94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194400"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="3709f-102">Метод ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="3709f-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="3709f-103">Возвращает имя константы.</span><span class="sxs-lookup"><span data-stu-id="3709f-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3709f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3709f-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3709f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3709f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3709f-106">[in] Длина буфера, `szName` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="3709f-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3709f-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения имени, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="3709f-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="3709f-108">[out] Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="3709f-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3709f-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3709f-109">Return Value</span></span>  
 <span data-ttu-id="3709f-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="3709f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3709f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3709f-111">Requirements</span></span>  
 <span data-ttu-id="3709f-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3709f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3709f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3709f-113">See also</span></span>

- [<span data-ttu-id="3709f-114">Интерфейс ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="3709f-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="3709f-115">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="3709f-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="3709f-116">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="3709f-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
