---
title: Метод ISymUnmanagedScope2::GetConstants
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176621"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="d81c8-102">Метод ISymUnmanagedScope2::GetConstants</span><span class="sxs-lookup"><span data-stu-id="d81c8-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="d81c8-103">Получает локальные константы, определяемые в этой области.</span><span class="sxs-lookup"><span data-stu-id="d81c8-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d81c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d81c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d81c8-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="d81c8-106">(в) Длина буфера, `pcConstants` на который указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="d81c8-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="d81c8-107">(ваут) Указатель на `ULONG32` то, что получает размер, в символах, буфера, необходимого для содержать константы.</span><span class="sxs-lookup"><span data-stu-id="d81c8-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="d81c8-108">(ваут) Буфер, который хранит константы.</span><span class="sxs-lookup"><span data-stu-id="d81c8-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d81c8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d81c8-109">Return Value</span></span>  
 <span data-ttu-id="d81c8-110">S_OK, если метод удается; в противном случае, E_FAIL или какой-либо другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d81c8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d81c8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d81c8-111">Requirements</span></span>  
 <span data-ttu-id="d81c8-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d81c8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81c8-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d81c8-113">See also</span></span>

- [<span data-ttu-id="d81c8-114">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="d81c8-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
