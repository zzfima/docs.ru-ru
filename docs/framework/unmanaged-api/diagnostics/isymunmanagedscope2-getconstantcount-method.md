---
title: Метод ISymUnmanagedScope2::GetConstantCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a063d25e180be466421c14ca65a5b4cea881fc8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127332"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="4b58b-102">Метод ISymUnmanagedScope2::GetConstantCount</span><span class="sxs-lookup"><span data-stu-id="4b58b-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="4b58b-103">Получает число констант, определенных в этой области.</span><span class="sxs-lookup"><span data-stu-id="4b58b-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b58b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b58b-104">Syntax</span></span>  
  
```  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b58b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b58b-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4b58b-106">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения констант.</span><span class="sxs-lookup"><span data-stu-id="4b58b-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b58b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4b58b-107">Return Value</span></span>  
 <span data-ttu-id="4b58b-108">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4b58b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b58b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4b58b-109">Requirements</span></span>  
 <span data-ttu-id="4b58b-110">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4b58b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b58b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4b58b-111">See also</span></span>

- [<span data-ttu-id="4b58b-112">Интерфейс ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="4b58b-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
