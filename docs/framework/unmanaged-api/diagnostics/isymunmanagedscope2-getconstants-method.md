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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08bc85c7a5b53c145375ca34f11ec499e5e7528f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096827"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="42020-102">Метод ISymUnmanagedScope2::GetConstants</span><span class="sxs-lookup"><span data-stu-id="42020-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="42020-103">Возвращает локальные константы, определенные в этой области.</span><span class="sxs-lookup"><span data-stu-id="42020-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42020-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42020-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42020-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="42020-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="42020-106">[in] Длина буфера, `pcConstants` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="42020-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="42020-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения констант.</span><span class="sxs-lookup"><span data-stu-id="42020-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="42020-108">[out] Буфер, который хранит константы.</span><span class="sxs-lookup"><span data-stu-id="42020-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42020-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="42020-109">Return Value</span></span>  
 <span data-ttu-id="42020-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="42020-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42020-111">Требования</span><span class="sxs-lookup"><span data-stu-id="42020-111">Requirements</span></span>  
 <span data-ttu-id="42020-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="42020-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42020-113">См. также</span><span class="sxs-lookup"><span data-stu-id="42020-113">See also</span></span>

- [<span data-ttu-id="42020-114">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="42020-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
